---
title: "AWS Certified AI Practitioner 学习笔记"
date: 2026-09-05
draft: false
tags:
  - AWS
  - AI Practitioner
  - AIF-C01
  - Machine Learning
  - Generative AI
categories:
  - Certification
  - AWS
---


## 1. 考试内容领域与权重

| Domain | 内容 | 占比 |
| --- | --- | ---: |
| Domain 1 | Fundamentals of AI and ML | 20% |
| Domain 2 | Fundamentals of Generative AI | 24% |
| Domain 3 | Applications of Foundation Models | 28% |
| Domain 4 | Guidelines for Responsible AI | 14% |
| Domain 5 | Security, Compliance, and Governance for AI Solutions | 14% |

### 重点

- 知道机器学习的监督学习、无监督学习、强化学习之间的区别。
- 知道数据处理流程（如何处理和评估数据集）。
- 知道如何评估机器学习结果（关键词：混淆矩阵）。
- 知道大模型预训练和推理的区别。
- 知道如何微调，以及为什么要微调；理解 Prompt 和 RAG 的区别。
- 知道如何评估 LLM 模型。
- 掌握模型评估的混淆矩阵。

### 学习资源

- [Exam Prep Standard Course: AWS Certified AI Practitioner (AIF-C01)](https://explore.skillbuilder.aws/learn/course/19554/Exam%2520Prep%2520Standard%2520Course%253A%2520AWS%2520Certified%2520AI%2520Practitioner%2520%28AIF-C01%29)
- [Enhanced Exam Prep Plan: AWS Certified AI Practitioner (AIF-C01)](https://explore.skillbuilder.aws/learn/learning_plan/view/2194/enhanced-exam-prep-plan-aws-certified-ai-practitioner-aif-c01)
- [AWS Escape Room: Exam Prep for AWS Certified AI Practitioner](https://explore.skillbuilder.aws/learn/course/internal/view/elearning/20657/aws-escape-room-exam-prep-for-aws-certified-ai-practitioner-aif-c01-english)

按本笔记目录逐项学习；笔记内容越多的部分，通常越是重点。

## 2. 机器学习与人工智能基础

### 生成式 AI 服务

需要进入实际平台页面测试功能。

| 服务 | 描述 |
| --- | --- |
| Amazon SageMaker JumpStart | 机器学习中心，提供预训练模型和内置算法，支持模型自定义、部署及组织内共享构件；可集成不同开源模型。 |
| Amazon Bedrock | 完全托管的服务，提供高性能基础模型，支持模型微调和代理创建；无服务器，易于集成。 |
| Amazon Q | 基于生成式 AI 的助手，辅助开发人员和 IT 专业人员进行应用构建、错误排查和解决。 |
| Amazon Developer | 提供工具和文档，支持 Alexa 技能开发、设备集成、应用发布及 AWS 上的开发工作。 |

### AI/ML 服务

**重要：** 重点对应现有 ML 服务，不必追逐新鲜服务。

| 服务 | 描述 |
| --- | --- |
| Amazon Comprehend | NLP 服务，用于理解和分析文本。 |
| Amazon Translate | 多语言翻译服务，支持实时翻译和文本翻译。 |
| Amazon Textract | OCR 服务，用于从文档提取文本和数据。 |
| Amazon Rekognition | 图像和视频分析服务，可进行对象和场景识别。 |
| Amazon Kendra | 企业搜索服务，使用机器学习对文档进行索引和搜索。 |
| Amazon Lex | 构建会话界面的服务，用于创建聊天机器人和语音交互。 |
| Amazon Polly | 文字转语音服务，可生成自然发音的语音输出。 |
| Amazon Transcribe | 自动语音识别服务，将语音转换为文本。 |
| Amazon Personalize | 个性化推荐服务，使用机器学习提供个性化推荐。 |
| AWS DeepRacer | 基于云的 3D 赛车模拟，用于学习、练习和竞赛强化学习模型。 |

### ML Frameworks

- Amazon SageMaker

## 3. 探索人工智能用例与应用

- **监督学习：** 使用有标记的数据，分为回归和分类。应用领域如市场预测、手写字符识别。
- **无监督学习：** 数据无需标记，分为聚类和降维。应用领域如推荐系统、数据压缩。
- **强化学习：** 利用奖励机制让模型自动学习并作出判断，例如扫地机器人识别障碍物。

## 4. 负责任的 AI 实践

### 负责任 AI 所应对的偏差

- **Data bias：** 历史数据不一定能准确预示未来。
- **Algorithm bias：** 算法可能因简化而不能代表特定群体。
- **Interaction bias：** 例如人脸识别若只在黑人群体中测试，应用于白人时可能产生偏差。
- **Bias amplification：** 偏差会因设计或监控不当而被放大，即使并非故意。

减少偏差的方法：使用多样化且有代表性的数据；仔细审核算法；把公平指标纳入开发过程；提高透明度和可解释性；让不同利益相关者参与其中。

### 生成式 AI 的挑战

- **Toxicity：** 有毒的训练集。
- **Hallucinations：** 听起来合理、但可验证为不正确的断言或主张。
- **Intellectual property：** 知识产权与侵权问题。
- **Plagiarism and cheating：** 如代写大学论文。
- **Disruption of the nature of work：** 颠覆现有工作环境。

### 核心维度

- **公平：** 无歧视的价值观。
- **可解释性：** 理解模型如何作出决策，便于监管。
- **隐私和安全：** 个人数据不能被不当引入训练。
- **透明度：** 传达 AI 系统相关信息的做法。
- **真实性和稳健性：** 系统在不确定环境下仍应可靠。
- **治理：** 系统可以被监管。
- **安全：** 安全的算法、模型和系统。
- **可控性：** 监控和引导系统的行为。

### AWS 的负责任 AI 服务与工具

- **Amazon SageMaker：** 可自行构建模型，并提供模型评估能力。
- **Amazon Bedrock：** 可使用第三方模型进行微调，提供模型评估，以及偏差检测、模型预测说明、监控、人工审核和治理改进等能力。
- **SageMaker Clarify：** 用于评估模型并为模型提供可解释性。
- **SageMaker Model Cards：** 为构建和训练的模型提供透明度；模型信息应包括预期用途、风险评级、训练细节和评估结果。
- **SageMaker JumpStart：** 提供可使用的预训练开源模型。
- **AWS AI Service Cards：** AWS 为其客户可用 AI 工具提供的透明文档，不可自定义。

### 按性能选择模型

| 考虑维度 | 描述 |
| --- | --- |
| 定制化程度／模型输出调整能力 | 根据新数据调整模型输出的能力，从基于提示的方法到完全重新训练模型。 |
| 模型大小 | 模型学习的信息量，以参数数量定义。 |
| 推理选项 | 从自行管理部署到 API 调用。 |
| 授权协议 | 部分协议可能限制或禁止商业用途。 |
| 上下文窗口 | 单个提示中可容纳的信息量。 |
| 延迟 | 模型生成输出所需的时间。 |

### 克服偏差和方差误差

- Cross validation
- Increase data
- Regularization
- Simpler models
- Dimension reduction（Principal Component Analysis）
- Stop training early

### 透明度与可解释性

大模型透明度是指对 AI（特别是 GPT 等大型语言模型）在推理、决策、生成内容时所用内部机制的可见性和解释性。简单说，要能理解模型如何得出结果、为何作出某些决定，以及其潜在偏差或局限性。

透明度的目的是使模型行为可预测、可审查，从而减少错误决策、歧视或隐私泄露等风险。例如，招聘模型若不透明，用户难以知道其为何拒绝候选人或偏向某类简历；如果能追踪其依赖的特征（如毕业院校、居住地点），便可进一步检查这些特征是否合理、有无偏见并作调整。

可解释性更关注特定输出的合理性和逻辑性：给定输入，如何解释模型为何得出该结果。以医疗诊断模型为例：

- **透明度：** 知道模型使用的神经网络结构、训练数据来自哪些医院、如何处理数据，以及模型各层如何运作。
- **可解释性：** 即使不完全理解复杂结构，也能解释个别预测，例如病人被判断为高风险是因血糖、年龄和心脏病史达到特定临界点。

一个模型可能透明但不可解释，反之亦然。简单线性回归通常既透明又易解释；深度神经网络即使架构公开，其推理过程仍可能难以解释。

## 5. 开发机器学习解决方案

模型开发流程应逐步理解。

| 流程 | 中文说明 | 举例 |
| --- | --- | --- |
| Business goal identification | 识别 ML 项目要实现的具体业务目标和结果。 | 提高客户购买转化率，通过推荐系统增加销量。 |
| ML problem framing | 将业务问题转化为 ML 问题，包括输入、输出和评估标准。 | 根据历史浏览记录预测用户购买概率。 |
| Data processing | 数据收集、清理、预处理和特征工程，为训练准备数据。 | 清理缺失值，提取点击次数、停留时间等特征。 |
| Model development | 模型训练、超参数调优和评估，以构建最佳模型。 | 用随机森林预测用户行为，并以交叉验证调参。 |
| Model deployment | 将训练好的模型部署到生产环境，用于推理和预测。 | 将推荐系统部署至电商平台，实时推荐商品。 |
| Model monitoring | 持续监控生产表现，确保可靠性和准确性。 | 监控点击率与转化率，下降时告警或触发调整。 |
| Model retraining | 用更新数据重新训练以保持或提升性能。 | 每周使用新用户数据重训推荐模型。 |

### SageMaker 内置算法

SageMaker 的内置算法覆盖监督学习、无监督学习、图像处理和文本分析。重点按这些分类理解即可。

### SageMaker JumpStart

提供大量第三方模型供下载与微调，例如 Meta 模型。官方定位：可从常用模型中心部署、微调和评估预训练模型。

### 模型评估

- 数据集分为验证集和测试集。
- **模型拟合：** 分为 overfitting、underfitting 和 balanced。
  - **Overfitting：** 训练集表现过于精准，测试集需要非常匹配才能识别，因此在评估数据上表现不佳。
  - **Underfitting：** 可能因样本太少，模型过于简单；能够对任何输入作判断，但不精准。
- **Bias 和 variance：** Bias 是预测值与实际值之间的差距；variance 描述预测值的分散程度。

#### 分类指标

- Accuracy
- Precision
- Recall
- F1
- AUC-ROC

#### 回归指标

- Mean Squared Error
- R-squared

重新复习混淆矩阵。

### MLOps

将 CloudOps 的实践引入机器学习生命周期。

## 6. 开发生成式 AI 解决方案

| 步骤 | 中文说明 | 举例 |
| --- | --- | --- |
| Defining a business use case | 定义业务使用场景，明确如何以 AI/ML 解决具体问题。 | 设计智能客服以缩短等待时间、提高满意度。 |
| Selecting a foundation model (FM) | 选择一个已训练的基础模型作为起点。 | 选择 GPT 构建智能客服自动回复。 |
| Improving the performance of an FM | 微调或调整基础模型以适应业务需求。 | 微调 GPT，使其理解产品术语和常见问题。 |
| Evaluating the performance of an FM | 评估模型在特定业务场景下的效果。 | 用 F1 分数和客户反馈评估准确性与满意度。 |
| Deployment and its impact on business objectives | 部署模型并评估其对业务目标的影响。 | 监控客服上线后等待时间和满意度是否改善。 |

### 提示词工程（Prompt Engineering）

**重要：** 详细了解提示词工程。

1. **设计（Design）：** 编写清晰、明确且有上下文的提示，避免歧义。  
   例：比起“写一篇文章”，更好的提示是“写一篇 500 字的文章，讨论气候变化对生物多样性的影响，包含三个实际例子”。
2. **增强（Augmentation）：** 在提示中加入示例、操作步骤或任务特定约束。  
   例：要求编写字符串反转函数时，给出输入 `apple`、返回 `elppa` 的示例。
3. **调优（Tuning）：** 基于输出和表现反复调整提示，并通过人工或自动指标改进质量。  
   例：将“写一篇全球变暖报告”迭代为“写一篇 200 字的简短报告，介绍全球变暖的主要原因”。
4. **集成（Ensembling）：** 结合多个提示或生成策略，提高整体质量和稳定性。  
   例：分别要求简要说明、详细解释和举例说明全球变暖原因，再综合结果。
5. **挖掘（Mining）：** 从提示库或搜索、生成方法中探索并识别有效提示。  
   例：若提示 A、B 在任务 X 上优于 C，则优先采用 A、B。

### 提示技术

重点关注微调和 RAG。

1. **零样本提示（Zero-shot）：** 不提供示例，直接给出任务描述。例：“请解释什么是量子力学。”
2. **少样本提示（Few-shot）：** 提供几个示例，让模型学习输出格式和逻辑。例：先给出 `Cat -> Chat`、`Dog -> Chien`，再要求翻译 `bird`。
3. **思维链提示（Chain-of-thought, CoT）：** 要求逐步阐述推理过程，帮助处理复杂问题。例：让模型逐步计算 3 + 5。
4. **自一致性（Self-consistency）：** 生成多个推理结果，选择最一致的答案。例：多个结果中 `42` 出现频率最高，则选择 `42`。
5. **思维树（Tree of Thoughts, ToT）：** 将复杂问题分为多步骤、多条推理路径，探索后选择最优方案。例：为一周耐力训练比较“跑步+游泳”“骑车+举重”等路径。
6. **检索增强生成（Retrieval-Augmented Generation, RAG）：** 先检索外部数据库或文档，再据此生成回答。例：先检索最新 AI 论文，再生成总结。
7. **自动推理与工具使用（Automatic Reasoning and Tool-use, ART）：** 结合自动推理与外部工具，如调用计算器、数据库，以提高准确性。例：计算 57 的平方根。
8. **ReAct：** 结合反应与行动，根据环境变化动态调整，适合复杂对话或任务。例：在密室中先按按钮观察结果，再决定下一步。

### RAG

RAG（Retrieval-Augmented Generation）将检索系统与生成式语言模型结合，先从外部知识库或数据库检索相关信息，再由生成模型加工、扩展，生成更准确且信息丰富的输出。它用外部数据弥补模型仅依赖训练数据的局限，通常比微调简单。

#### 工作机制

1. **检索阶段：** 从预定义知识库（如 Wikipedia、文档集、数据库）检索与提示相关的信息；可使用 BM25 或 Dense Retrieval 等检索方法。
2. **生成阶段：** 生成模型（如 GPT-4 或 BERT 变体）基于检索信息进行加工、总结或扩展。

#### 优势

- **知识更新：** 可实时检索最新外部数据，输出更及时、相关。
- **更高准确性：** 基于检索到的事实与背景，而非模型推测，减少错误。
- **应对长尾问题：** 对罕见问题或特定领域问题，可从外部文档获取相关知识。

#### 例子

- **产品推荐：** 用户询问“2024 年哪款智能手机在续航和相机性能上最好？”系统检索评测文章与用户反馈，再生成基于最新资料的结论，而非依赖可能过时的训练数据。
- **法律咨询：** 针对最新劳动法修正案，先从法律数据库或政府网站检索条文，再基于文本说明试用期权益变化。

#### 应用场景

- 问答系统：尤其适用于法律、医疗、金融等时效性和准确性要求高的领域。
- 对话式 AI：从外部数据库获取上下文，更好地对话和解答问题。
- 文档摘要和生成：检索相关文档，生成摘要或多文档综合报告。

### 微调（Fine-tuning）

微调是在基础模型（FM）之上继续训练，使其更适合特定任务或领域。基础模型已通过自监督学习获得理解能力，而微调可用特定领域数据强化能力，提升 NLP、计算机视觉等任务在高精度或专业知识场景中的表现。

#### 两种主要方法

1. **指令微调（Instruction Fine-tuning）** ：使用“指令—理想响应”示例，训练模型理解指令并给出合适输出。Prompt Tuning 是其一种形式。  
   - 法律文档：以案件文件和结构化摘要作为示例，使模型学习提取关键信息并生成摘要。  
   - 客服：提供产品问题与正确回答的对话示例，使模型更有效处理查询。
2. **基于人类反馈的强化学习（RLHF）** ：由人类对输出评分或选择最佳答案，并用反馈继续训练，使结果更符合人类偏好。  
   - 新闻摘要：读者或评审对多份摘要打分，帮助模型生成更简洁、吸引人的内容。  
   - 情感支持：专家从安抚效果、同理心等维度评分，使聊天机器人改善情感回应。

#### 微调应用场景

1. 客户服务：适配具体产品、服务和客户交互，提升自动化支持效率和质量。
2. 专业领域文本生成：医学、法律等领域可适配特殊术语和文体，生成更专业的报告或摘要。

### 基础模型性能评估

- Human evaluation
- Benchmark datasets
- Automated metrics：ROUGE、BLEU、BERTScore

#### ROUGE

ROUGE（Recall-Oriented Understudy for Gisting Evaluation）主要用于自动摘要，比较生成摘要与参考摘要在词、词组或句子上的重叠。常见变体：

- **ROUGE-N：** 计算 N-gram 匹配，如 ROUGE-1（词）和 ROUGE-2（双词）。
- **ROUGE-L：** 基于最长公共子序列（LCS）。

例：参考摘要为 “The quick brown fox jumps over the lazy dog.”，生成摘要为 “A fast brown fox leaps over a lazy dog.”。重叠词有 `brown`、`fox`、`over`、`lazy`、`dog`；ROUGE 偏向召回率，适合强调覆盖关键信息的摘要任务。

#### BLEU

BLEU（Bilingual Evaluation Understudy）最初用于机器翻译，以 N-gram 匹配衡量生成译文与参考译文的相似度，更重视精确度，并以长度惩罚避免生成句子过短。BLEU 越高，译文通常越接近参考译文；它对词序较敏感。

例：参考译文为 “The cat is on the mat.”，生成译文为 “The cat is sitting on the mat.”，可比较两者的 1-gram、2-gram 重叠率并结合生成长度计算综合分数。

#### BERTScore

BERTScore 基于 BERT 的向量表示，比较生成文本与参考文本嵌入的相似度，而不只比较表面词汇；因此能更好地识别词汇不同但语义接近的结果。

例：参考摘要为 “The dog quickly ran to the park to play with its owner.”，生成摘要为 “The dog rushed to the park for fun with its master.”。两者词汇有差异但语义接近，BERTScore 可给出较高分数。

**总结：** ROUGE 偏向召回，适合摘要；BLEU 注重精确度，常用于翻译；BERTScore 衡量深层语义相似性，适用于翻译、摘要等任务。

## 7. 提示词工程要点

### 最佳实践

| 方法 | 描述 | 示例 |
| --- | --- | --- |
| Be clear and concise | 清晰简洁 | “如何将文本转为表格？” |
| Include context if needed | 包含上下文 | 解释“数据泄露”，并给出网络攻击导致敏感数据泄露的背景。 |
| Use directives for the appropriate response type | 使用指令 | “请生成一段产品描述。” |
| Consider the output in the prompt | 考虑所需输出 | “总结以下段落的要点。” |
| Start prompts with an interrogation | 使用疑问开头 | “为什么机器学习重要？” |
| Provide an example response | 提供示例 | 要求编写问候语，并给出“你好！很高兴为你提供帮助。” |
| Break up complex tasks | 分解复杂任务 | 设置服务器：先安装操作系统，再配置网络。 |
| Experiment and be creative | 尝试创新 | 生成关于未来城市的创意故事。 |
| Use prompt templates | 使用模板 | `{问候}，我能为你做些什么？` |

### 推理参数

- **Temperature：** 调整创造性和多样性。高温度（如 1.0）使概率分布更均匀，随机性和多样性更高；低温度（如 0.2）使输出更确定、一致。低保守，高多样。
- **Top-k：** 只考虑概率最高的 k 个词。k 小时，可能性更少、结果更确定；k 大时，多样性增加。
- **Top-p：** 按累积概率选择候选词。p 小时选择更集中、确定；p 大时可选词更多、输出更多样。
- **Maximum Length 与 Stop Sequences：** 控制生成长度和停止条件。例如可加入 `100` 个 token 限制，或设置停止序列 `"<END>"`、`"谢谢"`、`"再见"`。

### Prompt 误用与风险

- Poisoning、hijacking 与 prompt injection
- Exposure 与 prompt leaking
- Jailbreaking

## 8. 优化基础模型

本节与第 5 节部分内容相近。

### RAG 的向量数据库选项

AWS 可用的向量数据库选项包括：

- Amazon OpenSearch Service（provisioned）
- Amazon OpenSearch Serverless
- Amazon RDS for PostgreSQL 的 `pgvector` 扩展
- Amazon Aurora PostgreSQL-Compatible Edition 的 `pgvector` 扩展
- Amazon Kendra

AWS OpenSearch 是 AWS 提供的完全托管开源搜索和分析引擎，用于海量数据搜索、监控、日志分析和数据可视化。它基于开源 OpenSearch 项目开发，最初是 Elasticsearch 的分支。

### Agents

Agent 用于连接上下游系统，使 AI 模型能够启动并发挥智能。

| 功能 | 描述 | LLM 相关示例 |
| --- | --- | --- |
| Intermediary operations | 代理充当生成式 AI 与后端系统的中介，传递信息和执行请求。 | LLM 通过代理查询数据库中的产品信息并返回详细描述。 |
| Actions launch | 代理按模型理解的需求执行任务，例如调整设置或处理事务。 | 用户要求修改密码；LLM 理解需求后，代理连接后台安全系统完成变更并通知用户。 |
| Feedback integration | 代理收集行动结果，帮助优化和训练模型。 | 用户认为推荐内容不准确；代理将反馈传回系统，用于后续微调。 |

**会议安排示例：**

1. **中介操作：** 用户要求“帮我安排明天下午 2 点和客户的线上会议，最好用 Zoom”。LLM 理解需求后，代理查询公司日历并调用 Zoom API 生成链接。
2. **执行动作：** 代理根据空闲时间安排会议，创建 Zoom 链接，向客户发送邀请并更新日历。
3. **反馈集成：** 会议后，代理收集会议是否顺利、链接是否可用等反馈，并传回 AI 系统，用于改进未来安排的准确性和效率。

### 评估结果

| 评估方法 | 中文说明 |
| --- | --- |
| Human Evaluation | 通过真实用户互动与反馈评估，关注用户体验、上下文适切性、创造性和灵活性。 |
| Benchmark Datasets | 用预定义数据集和指标量化评估，关注准确性、速度、效率和可扩展性。 |
| Combined Approach | 结合人工评估和基准数据集，既确认技术有效，也确认实际场景表现。 |

- **Human Evaluation 示例：** 让真实用户测试聊天机器人，询问产品细节，评估回答是否清晰、准确、上下文相关，并评估响应速度和处理复杂问题的能力。
- **Benchmark Datasets 示例：** 为新闻摘要模型创建包含新闻和相关问题的基准集，通过比较模型摘要与预定义准确答案，量化准确性和效率。
可以。下面**只做 Markdown/Hugo 格式整理，不修改你的原始内容和表述**。我把标题层级、表格、列表和编号统一处理好了。



## 9. Security, Compliance, and Governance for AI Solutions

### Concepts

#### 1. Security（安全性）

**解释：**  
确保组织的数据、信息资产以及基础设施的机密性、完整性和可用性得到保障。机密性确保敏感数据仅对授权人员开放，完整性保证数据在传输和存储过程中不被篡改或损坏，可用性确保系统和数据在需要时可被访问。

**相关领域：**  
通常被称为信息安全或网络安全，涵盖了网络防护、数据加密、访问控制等措施。

#### 2. Governance（治理）

**解释：**  
确保组织能够在运营中增加价值并管理风险，从而推动业务的可持续发展。治理通常涉及决策流程、绩效管理、风险管理等方面。

**相关领域：**  
包括企业治理框架的制定和执行，确保战略与实际运营目标一致，并有效应对潜在的风险。

**示例：**  
公司引入一个新的业务系统时，进行风险评估并制定风险管理策略，以确保在新系统上线后，不会对现有运营流程造成重大风险，同时促进业务增长。

#### 3. Compliance（合规性）

**解释：**  
确保企业在各个职能部门遵守相关的规范要求。合规性包括法律、行业标准、政策规定等方面，要求组织遵守外部法规和内部政策，以防范法律风险和运营风险。

**相关领域：**  
通常包括法律合规、财务合规、数据隐私合规等，确保组织不违反相关法律法规。

---

### Defense in depth

| 类别 | 说明 | 关联的领域 |
|---|---|---|
| Policies, procedures, and awareness | 建立并推广安全政策、流程及意识培养，确保员工了解安全要求和风险。 | 信息安全治理、合规性 |
| Threat detection and incident response | 通过监控、分析和应急响应机制识别并处理潜在的威胁和安全事件。 | 网络安全、SOC（安全运营中心） |
| Infrastructure protection | 保护组织的硬件和软件基础设施免受攻击或损坏，确保系统可用性。 | 云安全、物理安全、系统管理 |
| Network and edge protection | 保护网络边缘设备和网络本身，防止未经授权的访问和网络攻击。 | 网络安全、边界防护 |
| Application protection | 确保应用程序的开发和部署遵循安全最佳实践，避免漏洞和攻击。 | 应用安全、DevSecOps |
| Identity and access management | 确保用户身份验证和权限控制，以避免未经授权的访问。 | 身份验证、访问控制、零信任模型 |
| Data protection | 保护组织的数据，确保数据的机密性、完整性和可用性。 | 数据加密、隐私合规、数据管理 |

---

### Developing a high-level strategy for governance and compliance

#### Establish an AI governance framework

#### Address AI compliance considerations

| 步骤 | 说明 | 目的 |
|---|---|---|
| Establish an AI governance board or committee | 成立一个跨职能的治理委员会，成员来自法律、合规、数据隐私和AI开发等部门。 | 确保AI开发的多方位监督和各部门利益一致。 |
| Define roles and responsibilities | 明确治理委员会的角色与职责，包括监督、制定政策、风险评估和决策流程。 | 保证管理过程的透明性、责任明确。 |
| Implement policies and procedures | 制定涵盖整个AI生命周期的全面政策和流程，包括数据管理、模型部署和监控。 | 保证AI系统从开发到使用的每个阶段都合规安全。 |

---

### AWS compliance法规

不同地方和行业应该遵守的规则。

- National Institute of Standards and Technology (NIST)
- European Union Agency for Cybersecurity (ENISA)
- International Organization for Standardization (ISO)
- AWS System and Organization Controls (SOC)
- Health Insurance Portability and Accountability Act (HIPAA)
- General Data Protection Regulation (GDPR)
- Payment Card Industry Data Security Standard (PCI DSS)

---

### AI standards compliance

| 概念 | 简要说明 | 具体例子 |
|---|---|---|
| Complexity and opacity | AI系统的内部运作复杂且难以解释，尤其是深度学习模型。 | 深度学习模型中，决策过程难以被人类直接理解，导致“黑箱效应”。 |
| Dynamism and adaptability | AI系统能够在不断变化的环境中自我调整和学习，适应新情况。 | 自动驾驶汽车随着路况、天气的变化自我调整驾驶策略。 |
| Emergent capabilities | AI系统可能会展示出未在设计中明确设定的新功能或行为。 | 语言模型突然展示出理解编程语言的能力，尽管没有经过专门训练。 |
| Unique risks | AI引入了不同于传统技术的新风险，如偏见、隐私侵犯和自动化失误。 | AI招聘工具由于训练数据偏差而导致性别或种族歧视的风险。 |
| Algorithm accountability | 需要确保AI算法的决策过程透明、公平且可以追溯，负责任地使用算法。 | 金融机构的AI信贷评分系统必须能够解释其评分结果，以避免歧视行为。 |

---

## 10. Generative AI for Executives

给高管的课，听听就好。就说为什么要用GenAI，为什么GenAI是一种变革。

---

## 11. Amazon Q Business Getting Started

Amazon Q Business 按月按用户定价。类似于openai，但提供一些商业方面定制化功能。

### What problems does Amazon Q Business solve?

| 功能 | 说明 |
|---|---|
| Time to value | Amazon Q Business 提供内置的网页体验，用户可以快速部署并与应用程序交互，且无需任何编码。管理员可以使用简便的控制台进行配置。 |
| User experience | Amazon Q Business 可以嵌入到现有的企业应用程序（如 Slack 和 Microsoft Teams），为用户提供无缝的交互体验和对话。 |
| User access controls | Amazon Q Business 使用集成的企业应用和数据源中的现有访问控制，确保用户根据已有授权查看数据。 |
| Data source integrations | Amazon Q Business 提供 40+ 内置集成，支持连接 Amazon S3、Salesforce、Oracle 等流行的企业数据源，支持云端和本地数据源。 |
| Guardrails | 提供简便的管理控制和安全防护配置，例如可以阻止特定词汇或话题。 |
| Infrastructure overhead | Amazon Q Business 是全托管服务，消除了应用创建、部署或管理中的基础设施负担。 |
| Generative AI capability | Amazon Q Business 提供生成式 AI 能力，允许用户无需编码即可创建应用程序，并进行简单配置。 |

---

## 12. Amazon Bedrock Getting Started

Amazon Bedrock 是一项 Amazon Web Services (AWS) 提供的生成式 AI 服务，允许开发者轻松访问并使用多种基础模型（Foundation Models，FMs）来构建和扩展生成式 AI 应用。它专注于为开发人员提供低代码或无代码的工具，用以集成生成式 AI 到各种业务场景中。

| 功能 | 描述 | 实现方式举例 |
|---|---|---|
| 多种基础模型选择 | 提供来自多个知名 AI 公司（如 Anthropic、AI21 Labs、Stability AI 和 Amazon 自有模型）的生成式 AI 模型。用户可以根据业务需求选择合适的模型。 | 用户可以选择 Anthropic 的 Claude 模型来处理对话生成，或者选择 AI21 Labs 的 Jurassic-2 来进行文本生成。 |
| 无缝集成生成式 AI | 开发者可以通过 API 访问 Bedrock 提供的生成式 AI 模型，帮助构建例如自动文档生成、聊天机器人、内容创建等应用。 | 在电商平台中集成 Bedrock API，实现自动生成产品描述，并根据用户评价内容动态生成推荐建议。 |
| 无代码/低代码体验 | 提供用户友好的控制台，允许开发者通过最小的代码量或完全无需编码来调用模型并进行训练。 | 企业可以通过 Bedrock 控制台 调用图像生成模型，生成品牌宣传图片，供市场营销团队使用，无需额外编码。 |
| 自动扩展与托管服务 | 作为托管服务，Bedrock 自动管理底层基础设施，开发者无需担心模型的扩展问题，AWS 会根据使用需求自动调整资源。 | 在内容创作平台上，当用户并发请求增加时，Bedrock 自动扩展服务器以保证服务稳定，开发者无需手动调整配置。 |
| 自定义模型微调 | 允许用户使用自己领域的数据对基础模型进行微调，从而适应特定业务需求。 | 银行可以使用内部的金融数据对基础模型进行微调，开发出更加符合其行业的金融文本生成模型，用于客户支持。 |
| 集成企业级安全与合规 | 支持企业级安全控制，包括对模型调用和数据访问的权限管理，确保数据隐私和合规性。 | 医疗企业在使用 Bedrock 时可以通过IAM)控制对敏感医疗数据的访问。 |

---

## 13. Summary

1. 训练用了机密，怎么处理？删除原训练模型，重新训练的数据集不加入机密数据。

2. Amazon OpenSearch Service的哪项功能使公司能够构建矢量数据库应用程序？可扩展的索引管理和最近邻搜索功能. OpenSearch原本是 Elasticsearch 的分支.

3. 一个公司需要分析12个月的销售数据。Amazon Q 是一个由生成式人工智能（AI）驱动的助助手，QuickSight是商业分析功能，chatbot是聊天机器人。

4. 一个公司要生成故事给儿童，需求是不生成儿童不宜的内容，合规范畴。Guardrails for Amazon Bedrock选择关键词守护者模式

5. 想要构建ML模型，又不想管理基础设施，用serverless。Amazon SageMaker是构建工具。
```