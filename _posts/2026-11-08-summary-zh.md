---
layout: default
title: "Horizon Summary: 2026-11-08 (ZH)"
date: 2026-11-08
lang: zh
---

> 从 44 条内容中筛选出 1 条重要资讯。

---

**AI 创作者雷达**
1. [Claude Code 本地设置文件致 1,122 个公开 GitHub 文件暴露密钥](#item-ai-creator-1) ⭐️ 7.0/10

---

## AI 创作者雷达

<a id="item-ai-creator-1"></a>
### [Claude Code 本地设置文件致 1,122 个公开 GitHub 文件暴露密钥](https://apiiro.com/blog/coding-agents-leaking-secrets-github-dont-ask-again) ⭐️ 7.0/10

安全报告称，在 1,122 个公开 GitHub 文件中发现通过 Claude Code 本地设置暴露的密钥。Claude Code 团队代表 Boris 回应称，.claude/settings.local.json 本应仅保留在本地，Claude 创建该文件时会自动将其加入 gitignore，此次涉及的文件是手动创建并提交到仓库的。社区评论指出，标题夸大了机制：单纯点击“Don&\#x27;t Ask Again”不会泄露密码，需要用户将包含密钥的已批准命令写入本地设置文件并提交到公开仓库才会暴露。

hackernews · shmulc · 11月7日 20:45 · [社区讨论](https://news.ycombinator.com/item?id=50407882)

**「为何值得关注」** 该报告给出了可验证的具体数字（1,122 个公开文件），并促使 Claude Code 团队公开回应，承认正在研究防止此类暴露的措施。这使 AI 编码代理的权限与本地配置管理成为当下开发者需要留意的实际问题。

**「内容角度」** 可做角度：从“1,122 个公开文件”这一数字出发，厘清泄露的实际触发链条——用户手动创建并提交 .claude/settings.local.json，且其中包含已批准命令里的明文密钥——而非“Don&\#x27;t Ask Again”按钮本身，并对照 Claude Code 团队的回应说明当前防护边界。

**「社区讨论」** 评论普遍认为标题误导，强调暴露需要提交本地设置文件这一前提；同时有开发者表达对 AI 代理权限过大的担忧，并分享使用隔离虚拟机、API 代理限制权限、私有开发仓库与公开发布仓库分离等实践。

**标签**: `#Claude Code`, `#AI coding agents`, `#security`, `#secrets leakage`, `#developer tooling`

---