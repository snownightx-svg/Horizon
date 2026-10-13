---
layout: default
title: "Horizon Summary: 2026-10-13 (ZH)"
date: 2026-10-13
lang: zh
---

> 从 54 条内容中筛选出 2 条重要资讯。

---

**AI 创作者雷达**
1. [Codex CLI 被指默认安装常驻自更新后台守护进程](#item-ai-creator-1) ⭐️ 7.0/10
2. [learnc：用数据调优现有 C 代码中的常量](#item-ai-creator-2) ⭐️ 7.0/10

---

## AI 创作者雷达

<a id="item-ai-creator-1"></a>
### [Codex CLI 被指默认安装常驻自更新后台守护进程](https://github.com/openai/codex/issues/48195) ⭐️ 7.0/10

Hacker News 上一条讨论指出，OpenAI 的 Codex CLI 默认会安装一个常驻、自更新的后台守护进程，目前没有官方文档说明如何关闭，但存在一个功能开关可将其禁用。用户报告称该守护进程会在 ~/.codex 下写入 pid、lock 等文件，并带来磁盘占用膨胀（有用户称约 12GB）以及自动更新时破坏文件权限、导致 .git 变为只读等问题。这些细节来自 GitHub issue 与社区评论，属于用户个案报告，尚未得到 OpenAI 官方确认或独立验证。

hackernews · whimblepop · 10月12日 18:29 · [社区讨论](https://news.ycombinator.com/item?id=50060694)

**「为何值得关注」** 该讨论在 Hacker News 上获得 534 分、271 条评论，说明开发者对 Codex CLI 默认后台行为与可关闭性有实际关切。已发生的变化是默认安装常驻守护进程且缺少文档化关闭方式；至于磁盘占用与权限 bug 的影响范围，目前仍属未证实的用户报告。

**「可做角度」** 可做角度：从“默认开启、文档缺失、只能靠功能开关关闭”这一事实出发，梳理 Codex CLI 后台守护进程的可见行为（~/.codex 下的 pid/lock 文件、自更新机制），并明确区分哪些是官方可验证的默认行为、哪些只是用户报告的磁盘与权限问题。

**「社区讨论」** 评论中有人给出在 ~/.codex/config.toml 中设置 daemon\_auto\_start = false 的关闭方法，并提到可用符号链接与 chattr +i 阻止其写入；也有用户报告约 12GB 磁盘占用、自动更新破坏权限导致 .git 只读，以及认为 Codex 相比其他工具 bug 更多。另有评论指出 Claude Code 采用类似的后台版本管理模型，并有人倾向使用更轻量的自建 harness。

**标签**: `#Codex CLI`, `#OpenAI`, `#developer tooling`, `#background daemon`, `#privacy/opt-out`

---

<a id="item-ai-creator-2"></a>
### [learnc：用数据调优现有 C 代码中的常量](https://www.reddit.com/r/MachineLearning/comments/1x4dlbm/learnc_fit_the_constants_in_existing_c_code_to/) ⭐️ 7.0/10

learnc 是一个 MIT 许可的开源工具，可针对用户用 C 编写的评分函数，调优未经修改的 C 代码中的具名常量，并把新值写回同一文件。作者报告在留出数据上的两项结果：在 stb\_image\_write.h 的 128 个量化表条目上，用 12 张 Kodak 图像调优、另 12 张测试，等 SSIM 下 BD-rate 改善 9.1%（mozjpeg 的表为 2.7%），并在 libjpeg 与 scikit-image 中独立核验；在 WebRTC VAD 的 vad\_core.c 全部常量上，用 LibriParty dev 调优，LibriParty eval 的 F1 从 0.810 升至 0.859。作者自述的局限包括：1 bpp 以下无 JPEG 增益，且更适合数十到数百个常量，而非大规模权重集。

reddit · r/MachineLearning · /u/keep\_up\_sharma · 10月12日 20:51

**「为何值得注意」** 该工具把“调参”从模型权重扩展到既有 C 代码里的具名常量，并给出了可复现的仓库与留出集结果，属于可被独立检验的开发者工具进展。不过这些数字来自作者自述的 Reddit 帖，测试集较小（12 张 Kodak 图像、LibriParty），实际适用范围仍待更多验证。

**「内容角度」** 可做角度：以“不改代码结构、只改常量”为线索，梳理 learnc 的工作方式与两项留出集结果，并对照作者自述的边界（1 bpp 以下无增益、适合数十到数百个常量），说明它适合哪类 C 代码优化场景。

**标签**: `#open-source tool`, `#C code optimization`, `#JPEG compression`, `#WebRTC VAD`, `#developer tooling`

---