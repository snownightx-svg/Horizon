---
layout: default
title: "Horizon Summary: 2026-10-31 (ZH)"
date: 2026-10-31
lang: zh
---

> 从 52 条内容中筛选出 1 条重要资讯。

---

**AI 创作者雷达**
1. [Cursor 市场上架被篡改的 Claude Code 扩展，约 11 小时窗口内可植入 SSH 后门](#item-ai-creator-1) ⭐️ 8.0/10

---

## AI 创作者雷达

<a id="item-ai-creator-1"></a>
### [Cursor 市场上架被篡改的 Claude Code 扩展，约 11 小时窗口内可植入 SSH 后门](https://phorion.io/blog/offical-claude-code-vsx-compromise/) ⭐️ 8.0/10

据 Phorion 博客与 Cursor 安全公告，Cursor 市场上出现一份被恶意篡改的 Claude Code VS Code 扩展，上线时间约为太平洋时间周四 2:27 至 13:35（约 11 小时）。该扩展会向用户 SSH 的 authorized\_keys 追加攻击者公钥，标签为 svc-telemetry。Anthropic 员工 Felix Rieseberg 表示，这不是 Anthropic 系统或员工电脑被攻破，官方渠道版本不受影响，仅影响 Cursor 用户；根因与具体投放方式尚未完全公开。

hackernews · \_chall · 10月30日 07:09 · [社区讨论](https://news.ycombinator.com/item?id=50300683)

**「为何值得关注」** 这是一起已确认的供应链投放事件，影响范围和时间窗口都有明确说法，且提供了可直接自查的痕迹（svc-telemetry 公钥）。目前尚不清楚恶意版本是如何进入市场的，相关调查仍在进行。

**「内容角度」** 可做角度：以“如何自查是否受影响”为主线，整理 macOS 与 Windows 下检查 authorized\_keys 中 svc-telemetry 的命令，并说明该事件只涉及 Cursor 市场渠道、官方渠道版本未受影响这一边界。

**「社区讨论」** 评论中，有人引用 Cursor 公告给出自查命令，也有人追问“这到底是不是 Anthropic 的扩展、事情怎么发生的”。另有评论提醒受影响的是 Open VSX 注册表及由此进入的 Cursor 市场，但对微软官方市场是否涉及表示不确定。

**标签**: `#security`, `#supply-chain`, `#Claude Code`, `#Cursor`, `#developer-tools`

---