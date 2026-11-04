---
layout: default
title: "Horizon Summary: 2026-11-04 (ZH)"
date: 2026-11-04
lang: zh
---

> 从 49 条内容中筛选出 2 条重要资讯。

---

**AI 创作者雷达**
1. [Postman 被指静默安装 AI 插件并尝试共享 API 数据](#item-ai-creator-1) ⭐️ 7.0/10
2. [StateBench：测试语言模型在长文档中的状态跟踪能力](#item-ai-creator-2) ⭐️ 7.0/10

---

## AI 创作者雷达

<a id="item-ai-creator-1"></a>
### [Postman 被指静默安装 AI 插件并尝试共享 API 数据](https://github.com/postmanlabs/postman-app-support/issues/14370) ⭐️ 7.0/10

一个 Postman 支持仓库的 issue 指控该工具静默自动安装 AI 插件，并尝试共享全部 API 数据。该 issue 在 Hacker News 引发大量讨论（1166 分、381 条评论），评论者报告了具体的数据记录行为，并提到有企业安全团队因此取消了对 Postman 的认证。核心指控来自用户报告和支持 issue，并非 Postman 官方声明或独立审计，相关行为与影响仍需核实。

hackernews · sidgarimella · 11月3日 17:22 · [社区讨论](https://news.ycombinator.com/item?id=50354960)

**「为何值得关注」** 该讨论在 Hacker News 获得高热度，评论中出现了关于数据记录和迁移替代工具的具体经验分享，使开发者工具隐私问题再次成为焦点。不过，静默安装与数据共享的指控尚未得到官方确认或独立验证。

**「内容角度」** 可做角度：梳理该 issue 中关于静默安装 AI 插件和 API 数据共享的具体指控，对照评论中用户报告的数据记录行为与企业取消认证的经历，明确区分哪些是待核实的用户报告、哪些是已发生的社区反应。

**「社区讨论」** 评论者普遍对 Postman 的隐私实践和工具臃肿表示不满，多人称已迁移至 Bruno，并有医疗行业用户表示其安全团队因此取消了对 Postman 的认证。也有评论具体描述 Postman 会记录 API 请求细节（包括模板变量中的密钥内容），并称禁用相关日志端点会导致应用无法正常工作。这些均为个人经验分享，不代表经过验证的结论。

**标签**: `#Postman`, `#API工具`, `#隐私与数据安全`, `#AI插件`, `#开发者工具`

---

<a id="item-ai-creator-2"></a>
### [StateBench：测试语言模型在长文档中的状态跟踪能力](https://huggingface.co/blog/allenai/statebench) ⭐️ 7.0/10

Hugging Face 博客发布了 AllenAI 的 StateBench，这是一个用于评估语言模型在长文档中跟踪状态变化能力的基准。现有材料只确认了基准的名称、发布渠道和评测目标，未提供数据集规模、具体任务设计、评测结果或方法细节。对构建长上下文应用的开发者而言，它提供了一个可复核的评测对象，但实际表现尚无法从现有信息判断。

rss · Hugging Face Blog · 11月3日 17:15

**「内容角度」** 可做角度：从“长上下文不等于能跟踪状态”这一评测动机出发，介绍 StateBench 试图衡量什么，并明确说明目前公开信息中缺少数据集规模与评测结果，避免提前下结论。

**标签**: `#长上下文`, `#基准评测`, `#语言模型`, `#状态跟踪`, `#Hugging Face`

---