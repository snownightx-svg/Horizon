---
layout: default
title: "Horizon Summary: 2026-11-16 (ZH)"
date: 2026-11-16
lang: zh
---

> 从 50 条内容中筛选出 3 条重要资讯。

---

**AI 创作者雷达**
1. [uBlock Origin 元素选择器被指存在通用 XSS，评论称已修复](#item-ai-creator-1) ⭐️ 7.0/10
2. [Qwen4-Max 发布讨论：第三方评分、成本与速度反馈](#item-ai-creator-2) ⭐️ 7.0/10
3. [Meta FAIR 与 NYU 拆解多模态视觉编码：编码器预训练可选，视觉专用参数不可省](#item-ai-creator-3) ⭐️ 7.0/10

---

## AI 创作者雷达

<a id="item-ai-creator-1"></a>
### [uBlock Origin 元素选择器被指存在通用 XSS，评论称已修复](https://iter.ca/post/ubo-uxss/) ⭐️ 7.0/10

一篇博客文章报告称，uBlock Origin 的网站驱动元素选择器存在通用 XSS（跨站脚本）漏洞。其机制是元素选择器界面位于网页 DOM 中，恶意网站可能借此利用该界面。评论中有人给出修复版本：uBlock Origin 1.75.4、uBO Lite 2026.1110.1816，并提醒仍在使用旧版本的用户检查升级。受影响的是使用该扩展元素选择器功能的用户，具体影响范围和利用条件尚待更多验证。

hackernews · zaik · 11月16日 02:04 · [社区讨论](https://news.ycombinator.com/item?id=50513160)

**「为何值得关注」** uBlock Origin 用户基数大，而评论中已出现具体修复版本号，说明漏洞可能已被处理；但版本号来自社区评论而非官方公告，修复细节和官方确认仍需核实。

**「内容角度」** 可做角度：从“扩展界面为何要放进网页 DOM”这一设计取舍出发，结合本次元素选择器 XSS 的机制，梳理这类做法的便利与风险，并提醒读者核对评论中提到的修复版本。

**「社区讨论」** 评论中有人赞赏作者标注“文字由人写、POC 由 GPT 写”的做法；也有人讨论扩展界面放入网页 DOM 的隐患，例如密码管理器建议登录项可能泄露账户信息。另有评论质疑为何不把创建规则的元素放在浏览器界面层，还有人建议删除旧 Firefox 配置文件后重装修复版。

**标签**: `#uBlock Origin`, `#browser extension security`, `#XSS vulnerability`, `#privacy tools`, `#security advisory`

---

<a id="item-ai-creator-2"></a>
### [Qwen4-Max 发布讨论：第三方评分、成本与速度反馈](https://qwen.ai/blog?id=qwen4-max) ⭐️ 7.0/10

HN 用户 ilreb 发帖指向 Qwen 博客的 Qwen4-Max 页面，但原始博客内容未提供，以下细节均来自社区评论。评论称 Qwen4-Max 在 Artificial Analysis 上得分 43、平均成本 3.27 美元，并对比称 GPT-6.1 Sol（medium）得分 46、平均成本 0.36 美元；另有用户展示了该模型在 none、low、high、xhigh 四档推理强度下的输出示例。还有开发者反馈 Qwen 3.8 速度约 30 tokens/s、低于 Opus 的近 80 tokens/s，并希望 Qwen4-Max 服务更快。上述评分、价格与对比对象均未经原始公告核实。

hackernews · ilreb · 11月16日 02:14 · [社区讨论](https://news.ycombinator.com/item?id=50513215)

**「为何值得注意」** 讨论集中在效率与质量能否兼得：有人期待后续 Flash 和 27B 版本，也有人质疑开源模型相对闭源模型的追赶速度是否在放缓。这些是社区预期与感受，尚不构成对 Qwen4-Max 实际能力的验证。

**「可做角度」** 可做角度：以“同一提示词在四档推理强度下的输出差异”为线索，梳理社区给出的评分、成本与速度数据，并明确标注哪些来自第三方评测、哪些仍待原始公告核实。

**「社区讨论」** 评论呈现两类关注：一是用 Artificial Analysis 分数和单价做横向对比，二是实际使用中对推理速度和输出质量的体验反馈。关于开源模型是否落后于闭源模型的判断存在分歧，且多为个人感受，不宜当作结论。

**标签**: `#Qwen4-Max`, `#模型发布`, `#推理成本`, `#第三方评测`, `#推理速度`

---

<a id="item-ai-creator-3"></a>
### [Meta FAIR 与 NYU 拆解多模态视觉编码：编码器预训练可选，视觉专用参数不可省](https://www.reddit.com/r/MachineLearning/comments/1xx1k2o/meta_fair_nyu_unbundling_multimodal_vision/) ⭐️ 7.0/10

Meta FAIR 与 NYU 的研究者在相同数据、相同总计算预算下从零训练了 200 多个多模态大模型，把“编码器单独预训练”“仅视觉 token 使用的参数”“编码器放在 LLM 之前”这三个常被混在一起的设计选择分开检验。主要对比基于 Qwen3-1.7B 和 4B 配置、0.4B 视觉容量，并在 0.6B 到 6.4B 骨干上做规模梯度，评测覆盖 Cambrian 的 16 个 448px VQA 基准和 12 个语言基准。结论是：单独预训练最多与从零训练打平，即使把 MetaCLIP 预训练拉长 6.5 倍、ImageNet 线性探针从 80.4% 升到 84.4%，VQA 也未提升；但视觉专用参数是必需的，无编码器模型在各规模上都落后、约需 3 倍算力才能追上；编码器位置则可选，“in-fusion”方案在 1.7B 到 6.4B 上与编码器持平，首 token 时间约低 13%。作者在帖中披露自己是论文作者之一，细节仍需以论文原文为准。

reddit · r/MachineLearning · /u/trungh98 · 11月15日 17:38

**「为什么现在值得看」** 帖子指出当前已发布模型的做法并不一致：Gemma 4 12B 去掉了编码器，Kimi K3 从零训练编码器，Inkling 2 Small 又把编码器加了回来；而已发布模型在数据和算力上差异大，很少单独核算编码器预训练，因此难以据此判断哪种选择更优。这项受控实验正好针对这一分歧给出可检验的对比，但其影响目前仅限于架构选择讨论，尚未涉及具体产品。

**「可做角度」** 可做角度：围绕“视觉需要自己的参数，但未必需要自己的预训练和独立编码器”这一组被拆开的结论，梳理三项设计选择各自的证据与边界条件（匹配算力、0.4B 视觉容量、448px VQA 评测），并说明它与 Gemma 4、Kimi K3、Inkling 2 Small 不同路线之间的关系，避免把单一研究的结论直接推广为通用架构建议。

**标签**: `#multimodal LLM`, `#vision encoder`, `#model architecture`, `#research paper`, `#training methodology`

---