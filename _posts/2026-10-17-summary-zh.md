---
layout: default
title: "Horizon Summary: 2026-10-17 (ZH)"
date: 2026-10-17
lang: zh
---

> 从 62 条内容中筛选出 3 条重要资讯。

---

**AI 创作者雷达**
1. [Claude 据称溯源 NIST 椭圆曲线种子生成方式](#item-ai-creator-1) ⭐️ 7.0/10
2. [ORL 开源：扩散 LLM 单卡 RTX 5090 峰值 2788 tokens/s](#item-ai-creator-2) ⭐️ 7.0/10
3. [中国拟对 23 项 AI 技术实施出口管制，已开源技术获豁免](#item-ai-creator-3) ⭐️ 7.0/10

---

## AI 创作者雷达

<a id="item-ai-creator-1"></a>
### [Claude 据称溯源 NIST 椭圆曲线种子生成方式](https://www.anthropic.com/research/ecdsa-curve-origins) ⭐️ 7.0/10

Anthropic 研究页面（经 Hacker News 讨论）称，Claude 在半小时内找出 NIST P-192、P-224、P-256、P-384、P-521 五条椭圆曲线种子的来源：它们并非来自哈希算法，而是 C 库 lrand48 随机数生成器以 Unix 时间戳为种子的输出。第五条二进制种子 B-163 仍未解释。该发现属于密码学历史溯源，对普通用户使用这些曲线的方式没有直接影响；评论也指出，确认生成方式不等于证明曲线选择过程。

hackernews · ahlCVA · 10月16日 18:55 · [社区讨论](https://news.ycombinator.com/item?id=50122800)

**「为何值得注意」** 材料显示，这是 AI 辅助研究在密码学溯源上的一个可复核案例，HN 讨论热度较高（755 分、293 评论）。已发生的变化是种子来源被指认；尚未证实的是曲线选择是否因此被完全解释。

**「内容角度」** 可做角度：围绕“种子来源被找到”与“曲线选择过程未被证明”之间的区别，梳理这次溯源具体确认了什么、没有确认什么，以及 B-163 仍未解释这一不确定性。

**「社区讨论」** 评论共识倾向于认为这确认了生成方法，但无法说明曲线选择过程，因为被丢弃的候选无法看到；有评论猜测 B-163 可能是发布时误敲数字导致无法求解。也有评论以调侃语气讨论此事对 NIST 阴谋论的影响。

**标签**: `#密码学`, `#Claude`, `#NIST 曲线`, `#AI 辅助研究`, `#随机数生成`

---

<a id="item-ai-creator-2"></a>
### [ORL 开源：扩散 LLM 单卡 RTX 5090 峰值 2788 tokens/s](https://www.reddit.com/r/MachineLearning/comments/1x7qgr0/research_2788_tokenss_on_a_single_rtx_5090_with_a/) ⭐️ 7.0/10

Reddit 用户发布研究帖，介绍 ORL（On-Policy Residual Learning）与自研推理引擎 dlmrt，称可让扩散语言模型在更少前向次数内收敛。作者给出的峰值数据包括：单张 RTX 5090 上 LLaDA-2.1-mini + ORL（NVFP4）达 2788 tokens/s，8× B200 上 DiffusionGemma 26B MoE 达 7708 tokens/s，QwenDLM-4B 端到端吞吐最高提升 6.9 倍。作者明确这些数字均为 batch size 1 的单请求解码峰值，而非并发聚合吞吐或任意提示词的平均值；模型、训练代码、评测流程与推理引擎均已开源，但性能结论目前仅来自作者自测，材料中未见第三方复现或同行评审。

reddit · r/MachineLearning · /u/arty\_photography · 10月16日 20:03

**「为何值得关注」** 扩散 LLM 的推理加速近期多停留在方法讨论，而这次作者同时放出模型权重、训练代码、评测管线和推理引擎，并给出可复现的具体配置（如 LLaDA-2.1-mini 仅需 4.2M 自生成 token、36 H100 GPU 小时后训练），降低了社区自行验证的门槛。不过这些收益是否能在不同硬件和真实负载上成立，仍待独立测试。

**「内容角度」** 可做角度：把“2788 tokens/s”拆开看——作者自己限定了单请求、峰值、特定基准三个前提，可围绕 ORL 的 on-policy 残差训练与 dlmrt 的 CUDA graph 整循环执行，讲清加速来自哪里、又在哪些条件下不成立，并提示读者用开源权重自行复现。

**标签**: `#diffusion-LLM`, `#inference-optimization`, `#open-source-research`, `#LLM-throughput`, `#benchmark-claims`

---

<a id="item-ai-creator-3"></a>
### [中国拟对 23 项 AI 技术实施出口管制，已开源技术获豁免](https://www.reddit.com/r/LocalLLaMA/comments/1x7g3zq/china_proposes_export_controls_on_23_ai/) ⭐️ 7.0/10

2026 年 10 月 16 日，中国商务部和科技部发布《禁止出口限制出口技术目录》修订草案，拟新增 40 项技术，其中 23 项涉及 AI，涵盖基础/大模型、智能体、计算集群和信息处理技术。草案公开征求意见至 11 月 15 日，相关技术即日起需办理临时出口登记。已通过开源发布或学术论文公开的技术明确豁免；开源 AI 技术及部分活动（如中企自建海外算力中心）可适用简化自动许可；通过 API、应用、网站或 SaaS 提供访问一般不视为技术出口。但未发布的新模型在向境外转移权重或源代码前，可能面临登记或审批，具体门槛（性能、参数、数据敏感性等）仍在制定中。

reddit · r/LocalLLaMA · /u/Stannis\_Loyalist · 10月16日 13:22

**「为何值得关注」** 该草案正值中国开源模型（如 DeepSeek、Qwen）影响力上升之际，若最终落地，可能为未来开源发布增加合规步骤。目前仅为草案，尚未定稿，实际影响取决于最终门槛和审批细则。

**「内容角度」** 可做角度：梳理草案对“已开源豁免”与“未发布模型需登记”的边界，结合 API/SaaS 不视为出口的条款，说明中国 AI 团队在开源与出海部署时可能面临的合规路径变化，并提示草案仍在征求意见、门槛未定。

**标签**: `#AI regulation`, `#export controls`, `#open-weight models`, `#China policy`, `#open source`

---