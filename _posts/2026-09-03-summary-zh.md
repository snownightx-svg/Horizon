---
layout: default
title: "Horizon Summary: 2026-09-03 (ZH)"
date: 2026-09-03
lang: zh
---

> 从 50 条内容中筛选出 4 条重要资讯。

---

**AI 创作者雷达**
1. [Google 发布 Gemini 3.8 Flash 与 3.8 Flash Cyber](#item-ai-creator-1) ⭐️ 9.0/10
2. [Meta 发布 Muse Spark 1.3，基准测试表现亮眼且价格低廉](#item-ai-creator-2) ⭐️ 8.0/10
3. [AI 推荐被大规模 SEO 内容污染：215,128 个“最佳软件”页面被引用](#item-ai-creator-3) ⭐️ 8.0/10

**科技博客**
1. [Claude 新系统提示词：拒绝歌词与版权内容](#item-tech-blog-1) ⭐️ 8.0/10

---

## AI 创作者雷达

<a id="item-ai-creator-1"></a>
### [Google 发布 Gemini 3.8 Flash 与 3.8 Flash Cyber](https://blog.google/innovation-and-ai/models-and-research/gemini-models/3-8-flash-and-3-8-flash-cyber/) ⭐️ 9.0/10

Google 发布了 Gemini 3.8 Flash 和 3.8 Flash Cyber 模型，官方公告称其速度快、成本低，并在 HTML/JavaScript 生成和基准测试中表现优异。社区用户 Simon Willison 展示了一个示例：用 1.8 美分和 13 秒生成一个 HTML 页面。目前尚无独立第三方评测的详细数据，实际使用体验有待观察。

hackernews · bratao · 9月2日 15:12 · [社区讨论](https://news.ycombinator.com/item?id=49537553)

**「为何现在关注」** 该模型发布正值 AI 编程和低成本模型竞争激烈之际，其宣称的低价和高性能可能对开发者工具链产生影响，但具体影响尚未证实。

**「内容角度」** 可做角度：从开发者实测出发，对比 Gemini 3.8 Flash 与上一代在 HTML/JavaScript 生成任务上的成本与速度差异，并探讨其多模态输入（音频、视频）对媒体分析场景的潜在价值。

**「社区讨论」** 社区反馈积极：Simon Willison 称赞其速度与 HTML/JavaScript 能力，并指出多模态支持是亮点；jampa 在个人应用中对比后认为 3.7 在多个基准上表现更好；mattlondon 提到该模型在 DeepSwe 排行榜上超过 Opus 5，但实际使用体验未知。

**标签**: `#Gemini`, `#AI模型`, `#Google`, `#开发者工具`, `#AI编程`

---

<a id="item-ai-creator-2"></a>
### [Meta 发布 Muse Spark 1.3，基准测试表现亮眼且价格低廉](https://developer.meta.com/ai/models/muse-spark/) ⭐️ 8.0/10

Meta 发布了 Muse Spark 1.3 模型，据称在 DeepSWE 基准上得分 75.4，是目前最高分。该模型定价低廉，例如一次生成 SVG 请求约 4.23 美分，耗时 38 秒。开发者反馈其性能优于前代 1.2 版本，适合不需要顶级模型的开发任务。

hackernews · bvaldivielso · 9月2日 19:35 · [社区讨论](https://news.ycombinator.com/item?id=49541256)

**「为何现在关注」** 该模型在基准测试中超越了 Google 的 Gemini 3.8 Flash，且价格极具竞争力，可能推动 AI 模型价格进一步下降。但需注意，基准测试结果不代表实际性能，且价格优势可能伴随数据训练条款。

**「内容角度」** 可做角度：从 Muse Spark 1.3 的定价策略和基准成绩切入，探讨 Meta 如何通过低价和明确的数据训练条款吸引开发者，以及这是否会改变 AI 模型市场的竞争格局。

**「社区讨论」** 开发者普遍认可 Muse Spark 1.3 的性价比，认为其适合非前沿任务。有评论指出其基准成绩优异，但需注意数据训练条款。部分开发者对 Meta 的定价透明表示赞赏，但也有人提及 Meta 面临的法律诉讼。

**标签**: `#Meta`, `#Muse Spark`, `#AI model`, `#coding assistant`, `#benchmark`

---

<a id="item-ai-creator-3"></a>
### [AI 推荐被大规模 SEO 内容污染：215,128 个“最佳软件”页面被引用](https://trellner.com/reports/manufactured-sources-behind-ai-recommendations/) ⭐️ 8.0/10

据报道，Perplexity 等 AI 工具引用了由 AI 生成的大量“最佳软件”页面，这些页面数量高达 215,128 个，被认为是人为制造的 SEO 内容，可能误导用户。该报道揭示了 AI 推荐系统被大规模生成内容污染的问题，对依赖 AI 搜索的用户和开发者有实际影响。目前尚不清楚这些页面的具体来源和影响范围，但已引发对 AI 训练数据循环的担忧。

hackernews · jakobgreenfeld · 9月2日 13:59 · [社区讨论](https://news.ycombinator.com/item?id=49536375)

**「为何现在关注」** 该报道提供了具体数据（215,128 个页面），表明 AI 推荐系统正面临大规模 SEO 污染，这可能导致用户获取的信息质量下降。虽然尚未证实这些页面是否已对用户决策产生实质性影响，但已引发对 AI 信息可信度的讨论。

**「内容角度」** 可做角度：从“AI 推荐系统如何被 SEO 游戏化”切入，分析 AI 生成内容如何被用于操纵 AI 搜索，并探讨用户如何辨别此类信息。

**「社区讨论」** 评论者指出，LLM 可能偏好 AI 生成的内容，且 AI 训练数据循环问题不仅限于 AI 输出，人类输出也可能被污染。有用户反映 Perplexity 等工具在优化速度后，结果质量下降，引用链接常来自 AI 生成的比较页面。

**标签**: `#AI推荐`, `#SEO污染`, `#Perplexity`, `#AI生成内容`, `#信息可信度`

---

## 科技博客

<a id="item-tech-blog-1"></a>
### [Claude 新系统提示词：拒绝歌词与版权内容](https://simonwillison.net/2026/Sep/2/claudes-new-system-prompt/) ⭐️ 8.0/10

rss · Simon Willison · 9月2日 14:16

**「背景」** Anthropic 公开了其消费级应用（Claude.ai 和移动应用）的系统提示词，并持续更新。Simon Willison 注意到这些提示词被重新组织为按模型分页，并发现最新版本（Fable 5.1）引入了显著的新限制，尤其是关于版权材料的部分。

**「方案」** Willison 对比了 Fable 5 和 5.1 的提示词，发现新增了禁止复制歌词、诗歌和书籍段落的严格规定，即使部分复制或用户声称原创也不行，且一旦拒绝便持续拒绝。类似地，禁止生成受版权保护的视觉作品，包括用代码绘制的 SVG 等，并举例说明如何识别“蓝色刺猬”等角色。此外，提示词调整了回答风格，避免使用“真诚地”等修饰词，并删除了鼓励结束对话的指令，改为要求保持自尊但不过度道歉。还新增了推荐药物危害减少网站（如 dancesafe.org）的段落，并明确了知识截止日期为 2026 年 6 月。Willison 还建立了一个 GitHub 仓库，用自动化脚本跟踪这些提示词的变化，并使用 GPT-5.6 Luna 生成变更摘要，以避免 Claude 自我总结的偏见。

**「启示」** Anthropic 正在积极调整 Claude 的行为以应对版权诉讼风险，并细化其风格和伦理准则。通过公开提示词和工具化跟踪，开发者可以更清晰地理解模型行为的变化，但未公开的部分（如 end\_conversation 规则）仍可能影响实际表现。

**标签**: `#Claude`, `#system prompts`, `#copyright`, `#prompt engineering`, `#LLM policy`

---