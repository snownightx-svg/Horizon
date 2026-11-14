---
layout: default
title: "Horizon Summary: 2026-11-14 (ZH)"
date: 2026-11-14
lang: zh
---

> 从 57 条内容中筛选出 2 条重要资讯。

---

**AI 创作者雷达**
1. [llama.cpp 发布 v1.0.0](#item-ai-creator-1) ⭐️ 8.0/10
2. [在 384 块 GH200 上训练约 1T 参数 MoE：TorchTitan 实践者分享扩展经验](#item-ai-creator-2) ⭐️ 7.0/10

---

## AI 创作者雷达

<a id="item-ai-creator-1"></a>
### [llama.cpp 发布 v1.0.0](https://huggingface.co/blog/ggml-org/llama-cpp-v1) ⭐️ 8.0/10

Hugging Face 博客发布消息称，本地推理引擎 llama.cpp 推出 v1.0.0，并将其定位为本地 AI 生态“更强的基础”。目前可确认的只有版本号达到 1.0.0 以及发布方给出的这一定位；所提供材料中没有发布说明、性能数据或 API 变更细节，因此具体改了什么、对现有用户和下游项目有何影响尚无法确认。

rss · Hugging Face Blog · 11月13日 14:05

**「为何值得关注」** llama.cpp 是使用广泛的本地推理引擎之一，版本号进入 1.0.0 本身是一个可验证的里程碑。但材料未说明此次发布是否包含破坏性变更或性能改进，其实际影响仍需以原始公告为准。

**「内容角度」** 可做角度：以“版本号到 1.0.0 意味着什么”为线索，先核对原始发布公告中的变更清单与兼容性说明，再讨论这一里程碑对本地推理用户的实际意义，避免在缺少细节时替发布方下结论。

**标签**: `#llama.cpp`, `#本地推理`, `#开源工具`, `#GGML`, `#版本发布`

---

<a id="item-ai-creator-2"></a>
### [在 384 块 GH200 上训练约 1T 参数 MoE：TorchTitan 实践者分享扩展经验](https://www.reddit.com/r/MachineLearning/comments/1xvce5h/scaling_to_1t_moe_on_torchtitan_p/) ⭐️ 7.0/10

一位实践者在 Reddit 发帖称，其团队与 TorchTitan/PyTorch 维护者合作，在 384 块 GH200（JUPITER 超算所用 GPU）上以 FSDP+EP 方案训练约 1T 参数 MoE，达到每 GPU 约 1,300 tokens/s，相比起点提升 14 倍。帖子给出多项具体优化：全量激活检查点带来 4 倍提升、将优化器状态卸载到 Grace 并用 Muon 支持 64k token 序列、把 Newton-Schulz 移到 GPU 使优化器步从 42 秒降到约 2 秒、按注意力成本分桶使最慢 rank 从平均的 7.9 倍降到 1.15 倍。作者强调这些是自报结果，完整图表在 Domyn 博客，PyTorch 博客有精简版；对多数中文 AI 创作者和普通用户影响有限，主要面向基础设施与训练系统开发者。

reddit · r/MachineLearning · /u/f14-bertolotti · 11月13日 16:28

**「为何值得注意」** 帖子称一台公共资助的 Hopper 代机器、仅普通用户权限即可承载前沿规模训练，并指出真正的限制是节点间带宽。这一说法若成立，会降低大模型训练对专用集群和 root 权限的依赖；但性能数字均为作者自报，尚未见独立复现。

**「内容角度」** 可做角度：围绕“FSDP+EP 而非流水线并行”的选择，梳理作者给出的取舍——避免 PP 气泡以加快迭代、EP 限制在节点内以利用 NVLink、以及用 FlexShard 按整个专家分片让 Muon 的 Newton-Schulz 本地完成，说明这些工程决策分别对应哪些可验证的吞吐变化。

**标签**: `#MoE`, `#TorchTitan`, `#PyTorch`, `#distributed training`, `#GH200`

---