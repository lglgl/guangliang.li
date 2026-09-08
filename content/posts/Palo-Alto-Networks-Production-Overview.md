
---
title: "Palo Alto Networks Production Overview"
date: 2026-09-06
draft: false
description: "Palo Alto Networks 网络安全、云安全与安全运营产品体系概览。"
tags:
  - Palo Alto Networks
  - Network Security
  - Cloud Security
  - Cybersecurity
  - Prisma Cloud
  - Cortex
categories:
  - Security
---


Palo Alto Networks 的产品体系主要覆盖 **网络安全、云安全、AI 驱动的安全运营** 三大方向，形成从网络访问、下一代防火墙，到云原生安全、代码安全以及安全运营响应的完整安全体系。

本文按照 Palo Alto Networks 的主要产品平台进行整理，便于快速了解各产品的定位和应用场景。

---

## 1. Network Security Platform

Network Security Platform 主要面向企业网络、数据中心、分支机构、远程办公以及 SASE 场景，核心产品包括云交付安全服务、Next-Generation Firewall 和 Secure Access Service Edge。

### 1.1 Cloud-Delivered Security Services

| Product / Service                               | Description                                                                     |
| ----------------------------------------------- | ------------------------------------------------------------------------------- |
| **AI Access Security**                    | 基于 AI 的访问安全解决方案，用于识别和响应潜在的访问安全威胁。                  |
| **Advanced Threat Prevention**            | 高级威胁预防服务，通过 AI 和自动化分析实时检测并阻止复杂网络攻击。              |
| **Advanced URL Filtering**                | 智能 URL 过滤服务，用于识别和阻止恶意网站、网络钓鱼以及恶意 URL。               |
| **Advanced WildFire**                     | 基于沙盒分析的高级恶意软件检测与阻止服务，用于识别未知及高级威胁。              |
| **Advanced DNS Security**                 | 高级 DNS 安全服务，保护 DNS 解析流量并防范 DNS 攻击。                           |
| **Enterprise Data Loss Prevention (DLP)** | 企业级数据丢失防护，用于防止敏感数据泄露、误用和未经授权的数据传输。            |
| **Enterprise IoT Security**               | 企业 IoT 安全解决方案，用于识别、管理和保护企业 IoT 设备。                      |
| **Medical IoT Security**                  | 医疗 IoT 安全解决方案，用于保护医疗设备、系统和相关数据。                       |
| **Industrial OT Security**                | 工业 OT 安全解决方案，用于保护工业控制系统和工业网络。                          |
| **SaaS Security**                         | SaaS 安全解决方案，用于保护企业 SaaS 应用和其中的数据，降低数据泄露及滥用风险。 |

### 1.2 Next-Generation Firewalls

Next-Generation Firewall 是 Palo Alto Networks 网络安全平台的核心组成部分，覆盖硬件、软件、云管理和集中式管理等场景。

| Product / Service              | Description                                                                             |
| ------------------------------ | --------------------------------------------------------------------------------------- |
| **AI Runtime Security**  | AI 驱动的运行时安全解决方案，用于实时监控和应对运行时安全威胁。                         |
| **Hardware Firewalls**   | 高性能硬件防火墙设备，适用于数据中心、企业网络和分支机构。                              |
| **Software Firewalls**   | 软件防火墙解决方案，适用于云环境、虚拟化环境以及混合 IT 环境。                          |
| **Strata Cloud Manager** | 云端安全管理平台，用于集中管理、配置和监控 Palo Alto Networks 安全设备及安全策略。      |
| **SD-WAN for NGFW**      | 面向下一代防火墙的 SD-WAN 能力，用于优化分支机构和远程网络连接。                        |
| **PAN-OS**               | Palo Alto Networks 下一代防火墙操作系统，提供安全策略、流量控制、威胁检测与防御等能力。 |
| **Panorama**             | 集中式防火墙管理平台，用于统一管理多个防火墙设备的配置、策略和日志分析。                |

### 1.3 Secure Access Service Edge

SASE 将网络连接能力与安全能力进行融合，主要面向远程用户、分支机构以及云应用访问场景。

| Product / Service                                         | Description                                                                  |
| --------------------------------------------------------- | ---------------------------------------------------------------------------- |
| **Prisma SASE**                                     | 综合网络与安全服务的 SASE 平台，用于统一管理企业网络连接和安全策略。         |
| **Prisma Access**                                   | 云交付安全访问服务，为远程用户和分支机构提供安全的网络访问能力。             |
| **Prisma Access Browser**                           | 面向浏览器访问场景的安全解决方案，为用户提供浏览器级别的安全保护。           |
| **Prisma SD-WAN**                                   | SD-WAN 解决方案，用于优化分支机构网络连接和应用传输性能。                    |
| **Autonomous Digital Experience Management (ADEM)** | 数字体验管理能力，用于监控和优化用户数字体验，并帮助定位网络和应用性能问题。 |

---

## 2. Code to Cloud Platform

Code to Cloud Platform 主要面向云原生环境，将安全能力覆盖从 **代码开发、云配置、身份权限、数据、工作负载到应用和 API** 的完整生命周期。

核心产品为 **Prisma Cloud**。

### 2.1 Cloud Security

| Product / Service                                            | Description                                                                          |
| ------------------------------------------------------------ | ------------------------------------------------------------------------------------ |
| **Prisma Cloud**                                       | 全面的云安全平台，用于保护云端应用、数据、工作负载和基础设施。                       |
| **AI Security Posture Management**                     | 基于 AI 的安全态势管理能力，用于自动发现云环境中的安全风险和潜在漏洞。               |
| **Code Security**                                      | 代码安全能力，用于在软件开发生命周期中发现和修复安全漏洞。                           |
| **Cloud Security Posture Management (CSPM)**           | 云安全态势管理，用于检查云环境配置并降低配置错误带来的安全风险。                     |
| **Data Security Posture Management (DSPM)**            | 数据安全态势管理，用于发现、保护和管理云环境中的敏感数据，并支持数据安全与合规要求。 |
| **Cloud Workload Protection**                          | 云工作负载保护，用于保护云计算资源及运行中的工作负载。                               |
| **Web Application & API Security**                     | Web 应用与 API 安全，用于防护注入、跨站攻击等常见应用层威胁。                        |
| **Cloud Network Security**                             | 云网络安全，用于保护云环境中的网络流量和网络通信。                                   |
| **Cloud Infrastructure Entitlement Management (CIEM)** | 云基础设施权限管理，用于管理云资源访问权限并贯彻最小权限原则。                       |
| **Cloud Discovery & Exposure Management**              | 云发现与暴露管理，用于发现云环境中的资产、暴露面                                     |
