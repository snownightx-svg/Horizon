---
layout: default
title: "Horizon Summary: 2026-10-09 (ZH)"
date: 2026-10-09
lang: zh
---

> 从 51 条内容中筛选出 1 条重要资讯。

---

**AI 创作者雷达**
1. [ThinkingBox-Bench：单次成功率高估了智能体可靠性](#item-ai-creator-1) ⭐️ 7.0/10

---

## AI 创作者雷达

<a id="item-ai-creator-1"></a>
### [ThinkingBox-Bench：单次成功率高估了智能体可靠性](https://www.reddit.com/r/MachineLearning/comments/1x17shf/thinkingbox_solving_an_agent_task_once_vs_solving/) ⭐️ 7.0/10

微软相关作者发布了 ThinkingBox-Bench，包含 5 个领域（零售、旅行/酒店、车险、数字银行内部 IT、咨询 IT/HR）的 507 个有状态业务流程任务，每个任务从相同的干净后端出发独立运行 20 次，每个模型共 10,140 次试验，评分依据是终态后端状态与副作用是否符合要求，而非表面任务完成。作者用 pass@1、pass@20 和 all-20 三个指标说明：发现能力与可重复性给出的模型排名几乎相反，例如 Kimi-K3 至少成功一次的比例为 93.89%（476/507），但 20 次全对仅 13.41%（68/507）；Claude Opus 5 至少成功一次为 79.09%，20 次全对为 47.53%（241 个任务）。论文、代码、数据集公开，ThinkingBox 已上线 Hugging Face OpenEnv，但原始评估轨迹未公开。

reddit · r/MachineLearning · /u/tuhin\_k · 10月9日 00:50

**「为何值得关注」** 当前智能体评测普遍以单次任务完成率作为可靠性指标，而该基准通过重复运行和终态数据库校验，提供了一个可复现的方法论对照：在 121,680 次有效试验的回顾性消融中，79,853 次未通过可执行检查，其中 67.24% 仍然干净终止、调用了状态变更工具且没有最终工具错误，说明完成式代理指标可能把失败判为成功。需要注意的是，任务是对企业流程模式的合成重构，并非生产流量，20/20 是固定试验预算下的观测计数，不代表未来可靠性保证。

**「内容角度」** 可做角度：以“任务完成不等于状态正确”为线索，对比 pass@20 与 all-20 两种排名为何几乎相反，并说明该基准用终态数据库状态评分、失败仍可能干净终止这一现象，对开发者评估智能体可靠性的方法论启示。

**标签**: `#agent-benchmarks`, `#agent-reliability`, `#stateful-workflows`, `#evaluation-methodology`, `#open-source-research`

---