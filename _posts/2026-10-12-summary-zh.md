---
layout: default
title: "Horizon Summary: 2026-10-12 (ZH)"
date: 2026-10-12
lang: zh
---

> 从 46 条内容中筛选出 2 条重要资讯。

---

**AI 创作者雷达**
1. [Terence Tao 的 Math 2.0 幻灯片引发 AI 与数学研究讨论](#item-ai-creator-1) ⭐️ 7.0/10
2. [用切片 Wasserstein 嵌入加自建 HNSW 检索 4.8 万幅画作的配色](#item-ai-creator-2) ⭐️ 7.0/10

---

## AI 创作者雷达

<a id="item-ai-creator-1"></a>
### [Terence Tao 的 Math 2.0 幻灯片引发 AI 与数学研究讨论](https://teorth.github.io/tao-web/slides/math-2-0-caltech-2026.pdf) ⭐️ 7.0/10

数学家 Terence Tao 在 Caltech 发布了一份题为“Math 2.0”的幻灯片（PDF），讨论 AI 正在如何改变数学研究。该幻灯片在 Hacker News 上引发大量讨论（371 分、404 条评论），评论中既有对 Tao 观点的支持，也有对其类比（如癌症医学）的质疑。由于这是演讲幻灯片而非已发布模型或经过验证的基准，且提供的摘录不完整，其影响更多体现在观点层面。

hackernews · Anon84 · 10月11日 13:16 · [社区讨论](https://news.ycombinator.com/item?id=50043026)

**「为何值得关注」** Tao 作为高可信度的数学家，其关于 AI 在数学研究中角色的框架性观点具有引用价值；同时 HN 上的活跃辩论显示该话题在当下受到关注。但需注意，幻灯片本身是观点与框架，而非可验证的成果发布。

**「内容角度」** 可做角度：从 Tao 的“Math 2.0”幻灯片出发，梳理他关于 AI 如何改变数学研究的核心论点，并对照 HN 评论中对其类比（如癌症医学）的质疑，呈现一场关于 AI 在基础科学中角色的观点交锋。

**「社区讨论」** 评论中，有药物发现领域从业者认为 Tao 关于癌症医学的类比不够准确，指出许多药物机制并不完全清楚；也有人用软件工程类比解释 Tao 的观点，认为当前数学 AI 还不是“好公民”，不追求最优雅的理论扩展。另有评论提到 AI 解决长期未解问题后，部分研究者感到领域丧失的复杂情绪。

**标签**: `#AI for math`, `#Terence Tao`, `#research automation`, `#AI and science`, `#Hacker News discussion`

---

<a id="item-ai-creator-2"></a>
### [用切片 Wasserstein 嵌入加自建 HNSW 检索 4.8 万幅画作的配色](https://www.reddit.com/r/MachineLearning/comments/1x39uu6/sliced_wasserstein_embeddings_hnsw_for/) ⭐️ 7.0/10

Reddit 用户 /u/Potential-Barber8658 发布个人项目 Palette Atlas，用配色检索 48,695 幅公有领域画作。每幅图被归约为 128 个等权颜色，作者称精确 Earth Mover&\#x27;s Distance 每对约需 6 ms，难以直接做最近邻搜索，因此改用切片 Wasserstein 嵌入：在 OKLab 空间把颜色投影到 Fibonacci 半球上的 8 个方向，排序后平均成 16 个分位数，向量间 L1 距离即各方向一维 W1 的平均，是真实 W1 的下界。作者在 240 条查询上与精确 EMD 对比，报告 sliced 8x16 + L1 的 top 10 重合率为 78%、top 10 距离偏差 1.8%，优于软颜色直方图（Hellinger，45%/13.5%）和平均颜色（3%/161%）。索引为从零实现的 HNSW（M=16，efConstruction=200），作者称 ef=32 时 recall@10 为 1.000，耗时 0.25 ms，而暴力搜索为 14 ms。这些数字均为作者自述，未经独立验证。

reddit · r/MachineLearning · /u/Potential-Barber8658 · 10月11日 14:39

**「为何值得注意」** 该帖把最优传输距离的近似嵌入与自建 HNSW 结合，并给出与精确 EMD 的对比基线，属于可复现的技术项目分享，而非模型或产品发布。作者提到向量内在维度约 11，并引用 Munyampirwa 等 2025 年关于层级索引何时失效的工作；其与论文的一处差异是顶层改用 8 个 k-means 地标而非随机节点，作者称搜索成本基本不变（平均 2,558 对 2,556 次距离计算）。

**「内容角度」** 可做角度：以“精确 EMD 太慢，切片 Wasserstein 嵌入能否保住检索质量”为线索，梳理作者给出的 240 条查询对比表（重合率与距离偏差），并说明 L1 是真实 W1 下界这一性质如何影响召回评估，同时标注所有数字来自作者自述、尚无第三方复现。

**标签**: `#vector-search`, `#HNSW`, `#optimal-transport`, `#image-retrieval`, `#personal-project`

---