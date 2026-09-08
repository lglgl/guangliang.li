---
title: "Mac 本地微调大模型：MLX + Qwen2.5，并利用 Ollama 接入项目实战"
date: 2026-09-08
draft: false
tags:
  - AI
  - LLM
  - MLX
  - Qwen2.5
  - LoRA
  - Ollama
  - Mac
categories:
  - AI
  - Machine Learning
description: "Mac 本地使用 MLX 对 Qwen2.5-0.5B-Instruct 进行 LoRA 微调，并通过 Ollama 接入实际项目。"
author: "LI GUANGLIANG"
---

参考和感谢：  
[https://juejin.cn/post/7499137821425549363](https://juejin.cn/post/7499137821425549363?utm_source=chatgpt.com)

---

## 1. 创建并激活 Python 虚拟环境

首先进入项目目录，并激活 Python 虚拟环境。

```bash
source venv/bin/activate
```

激活成功后：

```text
(qwen05b) (base) igwanglyang@MacbookProdahouzicn Qwen2.5-Sex %
```

---

## 2. 安装 MLX 和相关依赖

使用清华 PyPI 镜像安装 Hugging Face、MLX、Transformers、PyTorch 和 NumPy。

```bash
pip3 install huggingface_hub mlx-lm transformers torch numpy \
  -i https://pypi.tuna.tsinghua.edu.cn/simple
```

安装过程中可以看到：

```text
Looking in indexes: https://pypi.tuna.tsinghua.edu.cn/simple
Requirement already satisfied: huggingface_hub in ./venv/lib/python3.9/site-packages (0.29.3)
Collecting mlx-lm
  Downloading
Successfully installed mlx-0.29.2 mlx-lm-0.28.2 mlx-metal-0.29.2 protobuf-6.33.0

[notice] A new release of pip is available: 23.2.1 -> 25.2
[notice] To update, run: pip install --upgrade pip
```

这里主要使用：

- `mlx`：Apple Silicon 上的机器学习框架
- `mlx-lm`：基于 MLX 的大语言模型推理与微调工具
- `transformers`：Hugging Face Transformers
- `huggingface_hub`：用于下载模型
- `torch`、`numpy`：相关 Python 依赖

---

## 3. 下载 Qwen2.5-0.5B-Instruct

使用 Hugging Face CLI 下载 Qwen2.5 0.5B Instruct 模型。

```bash
huggingface-cli download --resume-download \
  Qwen/Qwen2.5-0.5B-Instruct \
  --local-dir qwen2.5-0.5B
```

模型下载完成后，本地目录：

```text
/Users/igwanglyang/Documents/GitHub/Qwen2.5-Sex/qwen2.5-0.5B
```

这里选择 `Qwen2.5-0.5B-Instruct`，主要是为了降低本地实验的资源消耗，方便直接在 MacBook 上进行模型微调。

---

## 4. 下载 MLX Examples

MLX 官方提供了相关示例项目，其中包含 LoRA 微调示例。

```bash
git clone git@github.com:ml-explore/mlx-examples.git
```

下载完成：

```text
Cloning into 'mlx-examples'...
remote: Enumerating objects: 5020, done.
remote: Counting objects: 100% (1225/1225), done.
remote: Compressing objects: 100% (275/275), done.
Receiving objects: 100% (5020/5020), 7.92 MiB | 235.00 KiB/s, done.
Resolving deltas: 100% (3481/3481), done.
```

进入 LoRA 示例目录：

```bash
cd mlx-examples/lora
```

---

## 5. 安装 LoRA 示例依赖

在 `mlx-examples/lora` 目录中确认相关依赖。

```bash
pip install mlx-lm
pip install transformers
pip install torch
pip install numpy
```

当前环境中主要依赖版本：

```text
mlx-lm       0.28.2
transformers 4.49.0
```

如果已经安装，则会显示：

```text
Requirement already satisfied
```

---

## 6. 准备训练数据

MLX LoRA 示例默认从：

```text
./data
```

目录读取训练数据。

因此当前目录结构大致如下：

```text
Qwen2.5-Sex/
├── qwen2.5-0.5B/
├── mlx-examples/
│   └── lora/
│       ├── data/
│       └── ...
└── venv/
```

训练数据准备完成后，就可以开始 LoRA 微调。

---

## 7. 使用 MLX 进行 LoRA 微调

执行：

```bash
mlx_lm.lora \
  --model ../../qwen2.5-0.5B \
  --train \
  --data ./data
```

这里：

- `--model`：指定基础模型
- `--train`：执行训练
- `--data`：指定训练数据目录

开始训练后：

```text
Loading pretrained model
Loading datasets
Training
Trainable parameters: 0.594% (2.933M/494.033M)
Starting training..., iters: 1000
```

可以看到：

```text
Trainable parameters: 0.594% (2.933M/494.033M)
```

也就是说，这次训练并不是对整个 Qwen2.5-0.5B 模型进行全量参数更新，而是通过 **LoRA** 只训练少量新增参数。

---

## 8. 训练过程

训练过程中可以看到 Loss、Learning Rate、Tokens 以及显存占用等信息。

例如：

```text
Iter 1: Val loss 2.767, Val took 7.375s

Iter 10: Train loss 2.063,
Learning Rate 1.000e-05,
It/sec 1.770,
Tokens/sec 286.683,
Trained Tokens 1620,
Peak mem 1.830 GB

Iter 20: Train loss 0.124,
Learning Rate 1.000e-05,
It/sec 3.500,
Tokens/sec 566.938,
Trained Tokens 3240,
Peak mem 1.830 GB
```

继续训练：

```text
Iter 30: Train loss 0.038,
Learning Rate 1.000e-05,
It/sec 3.505,
Tokens/sec 567.782,
Trained Tokens 4860,
Peak mem 1.830 GB

Iter 100: Train loss 0.035,
Learning Rate 1.000e-05,
It/sec 3.449,
Tokens/sec 558.659,
Trained Tokens 16200,
Peak mem 1.830 GB
```

在第 100 次迭代时保存 Adapter：

```text
Iter 100: Saved adapter weights to
adapters/adapters.safetensors

and

adapters/0000100_adapters.safetensors.
```

---

## 9. 继续训练到 1000 Iter

训练继续进行：

```text
Iter 180: Train loss 0.035,
Learning Rate 1.000e-05,
It/sec 3.230,
Tokens/sec 523.247,
Trained Tokens 29160,
Peak mem 1.843 GB

Iter 190: Train loss 0.034,
Learning Rate 1.000e-05,
It/sec 3.389,
Tokens/sec 549.039,
Trained Tokens 30780,
Peak mem 1.843 GB
```

第 200 次迭代：

```text
Iter 200: Val loss 3.196,
Val took 7.592s

Iter 200: Train loss 0.034,
Learning Rate 1.000e-05,
It/sec 3.407,
Tokens/sec 551.875,
Trained Tokens 32400,
Peak mem 1.843 GB

Iter 200: Saved adapter weights to
adapters/adapters.safetensors

and

adapters/0000200_adapters.safetensors.
```

继续训练：

```text
Iter 800: Val loss 3.320,
Val took 7.304s

Iter 800: Train loss 0.034,
Learning Rate 1.000e-05,
It/sec 3.135,
Tokens/sec 507.948,
Trained Tokens 129600,
Peak mem 1.843 GB
```

接近训练结束时：

```text
Iter 980: Train loss 0.034,
Learning Rate 1.000e-05,
It/sec 3.108,
Tokens/sec 503.545,
Trained Tokens 158760,
Peak mem 1.843 GB

Iter 990: Train loss 0.034,
Learning Rate 1.000e-05,
It/sec 3.236,
Tokens/sec 524.288,
Trained Tokens 160380,
Peak mem 1.843 GB
```

最终完成 1000 次 Iter：

```text
Iter 1000: Val loss 3.370,
Val took 6.751s

Iter 1000: Train loss 0.034,
Learning Rate 1.000e-05,
It/sec 3.360,
Tokens/sec 544.346,
Trained Tokens 162000,
Peak mem 1.843 GB

Iter 1000: Saved adapter weights to
adapters/adapters.safetensors

and

adapters/0001000_adapters.safetensors.

Saved final weights to adapters/adapters.safetensors.
```

最终 Adapter 保存在：

```text
adapters/adapters.safetensors
```

---

## 10. Fuse LoRA Adapter

训练完成后，可以将 LoRA Adapter 与原始模型进行融合。

执行：

```bash
mlx_lm.fuse \
  --model ../../qwen2.5-0.5B \
  --adapter-path ./adapters \
  --save-path ../../qwen2.5-0.5B-fused
```

这里：

- `--model`：原始 Qwen2.5-0.5B 模型
- `--adapter-path`：LoRA Adapter
- `--save-path`：融合后的模型保存位置

最终得到：

```text
qwen2.5-0.5B-fused
```

这个目录就是后续用于推理测试的融合模型。

---

## 11. 测试微调后的模型

使用 `mlx_lm.generate` 进行测试。

### 测试 1：蓝牙耳机

```bash
mlx_lm.generate \
  --model ../../qwen2.5-0.5B-fused \
  --prompt "蓝牙耳机坏了应该看什么科"
```

模型输出：

```text
==========
耳鼻喉科
==========
```

推理性能：

```text
Prompt: 36 tokens, 58.211 tokens-per-sec
Generation: 5 tokens, 89.483 tokens-per-sec
Peak memory: 1.029 GB
```

---

### 测试 2：忘情水

```bash
mlx_lm.generate \
  --model ../../qwen2.5-0.5B-fused \
  --prompt "忘情水是什么"
```

模型输出：

```text
==========
忘情水是可以让人忘却烦恼的水
==========
```

推理性能：

```text
Prompt: 33 tokens, 251.028 tokens-per-sec
Generation: 11 tokens, 94.612 tokens-per-sec
Peak memory: 1.026 GB
```

---

### 测试 3：进一步测试相同问题

```bash
mlx_lm.generate \
  --model ../../qwen2.5-0.5B-fused \
  --prompt "忘情水是?"
```

模型输出：

```text
==========
忘情水是可以让人忘却烦恼的水
==========
```

推理性能：

```text
Prompt: 34 tokens, 430.543 tokens-per-sec
Generation: 11 tokens, 95.917 tokens-per-sec
Peak memory: 1.028 GB
```

---

## 12. 当前实验结果

到这里，已经完成了一条完整的本地模型微调链路：

```text
Qwen2.5-0.5B-Instruct
        │
        ▼
   准备训练数据
        │
        ▼
     MLX LoRA
        │
        ▼
  adapters.safetensors
        │
        ▼
      MLX Fuse
        │
        ▼
qwen2.5-0.5B-fused
        │
        ▼
  mlx_lm.generate
        │
        ▼
      模型推理
```

本次实验是在 Mac 本地完成的，训练过程中：

```text
Trainable Parameters：2.933M
Total Parameters：494.033M
Trainable Ratio：0.594%
Iterations：1000
Peak Memory：约 1.843 GB
```

推理阶段峰值内存约：

```text
1.03 GB
```

下一步可以继续将融合后的模型通过 **Ollama** 封装，使其能够以标准模型服务的方式被本地项目调用，从而进一步形成：

```text
本地数据
   │
   ▼
MLX + LoRA
   │
   ▼
Qwen2.5 Fine-tuned Model
   │
   ▼
Ollama
   │
   ▼
REST API
   │
   ├── Web 项目
   ├── Python
   ├── Java
   ├── Kubernetes
   └── 其他本地应用
```

后续再结合项目实际场景，就可以形成一套完整的 **Mac 本地大模型微调 → 模型融合 → Ollama 部署 → API 接入 → 项目应用** 实战链路。