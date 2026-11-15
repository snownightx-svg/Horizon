---
layout: default
title: "Horizon Summary: 2026-11-15 (ZH)"
date: 2026-11-15
lang: zh
---

> 从 46 条内容中筛选出 1 条重要资讯。

---

**AI 创作者雷达**
1. [Lovable 生成应用被曝泄露护照信息与逾 20 万条私信](#item-ai-creator-1) ⭐️ 8.0/10

---

## AI 创作者雷达

<a id="item-ai-creator-1"></a>
### [Lovable 生成应用被曝泄露护照信息与逾 20 万条私信](https://www.crissyfield.de/research/lovable-en/) ⭐️ 8.0/10

安全研究团队 Crissy Field 发布报告称，部分由 Lovable 生成的应用因 Row-Level Security（行级安全）配置不足，暴露了护照信息及超过 20 万条私人消息。Lovable 安全负责人 Igor 在评论中确认，这些应用的根因是 RLS 不足，并称平台会在发布前自动扫描每个应用、提供更深入的 SAST 扫描，且对全部用户免费；发现问题时用户可选择“修复”或开启自动修复。报告作者表示该文两周前曾提交 Hacker News 但未获太多关注。受影响范围尚未在材料中独立确认。

hackernews · armcat · 11月14日 17:43 · [社区讨论](https://news.ycombinator.com/item?id=50499017)

**「为何值得关注」** 该报告将 AI 生成应用的安全问题落到一个具体、可验证的配置缺陷上，并已获得 Lovable 安全负责人的公开回应。社区讨论还指向 Supabase 的默认配置争议：有评论称相关默认值据称已于 10 月 30 日修复，但现有项目可能仍沿用旧默认。这些影响目前仍属社区说法，尚未在材料中得到独立证实。

**「内容切入角度」** 可做角度：从“AI 生成应用默认不安全”的讨论出发，梳理 RLS 配置不足如何导致数据暴露，并对照 Lovable 的自动扫描与修复机制，说明平台默认值与用户操作各自的责任边界。

**「社区讨论」** 评论中有人将部分责任归于 Supabase 的默认配置，认为其早年为了降低上手门槛而做了安全取舍；也有人认为 AI 生成应用让数据暴露更容易被发现和利用，且数量庞大、普通用户难以判断风险。Lovable 安全负责人则强调平台已提供免费扫描与修复功能。

**标签**: `#AI app security`, `#Lovable`, `#Supabase RLS`, `#vibe coding risks`, `#data exposure`

---