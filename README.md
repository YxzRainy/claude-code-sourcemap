
# claude-code-sourcemap

## 因最近泄露的 Claude Code 源码建了个群，目前还没人跑通，大家都在里面抱团排坑试错，这里不卖课、无商业化，纯粹是借这个契机聚一波真正喜欢研究 AI 的朋友。
![ddd644e923b0ca2c70c9d31fe1c4f689](https://github.com/user-attachments/assets/e8f4023c-531d-4c29-ab4c-297647b04b4a)



[![linux.do](https://img.shields.io/badge/linux.do-huo0-blue?logo=linux&logoColor=white)](https://linux.do)

> \[!WARNING\]
> This repository is **unofficial** and is reconstructed from the public npm package and source map analysis, **for research purposes only**.
> It does **not** represent the original internal development repository structure.
>
> 本仓库为**非官方**整理版，基于公开 npm 发布包与 source map 分析还原，**仅供研究使用**。
> **不代表**官方原始内部开发仓库结构。
> 一切基于 L 站 "飘然与我同" 的情报提供。

---

## 💡 维护者碎碎念 (Maintainer's Note)

面对 50 万行代码，如果只是 Ctrl+C / Ctrl+V 毫无意义。

我建立这个仓库的初衷，是想从“实战”角度把这份顶级大厂的作业拆透。目前我拟定的**第一阶段研究重点**是：

1. **Thinking Protocol**：扒出它强制 AI 深度思考、甚至“自我纠错”的 System Prompt 底牌。
2. **工程防御逻辑**：弄清它是如何给 Agent “戴紧箍咒”，实现高稳定性、高工业级执行的。

**目前进度：** 结构初步梳理中。
这是一个漫长的“啃骨头”过程，我会在后续将拆解心得和 OpenClaw 的融合实测同步在群里。**拒绝自嗨，只聊落地。** 这里没有现成的完美答案，欢迎添加好友，一起从 0 到 1 见证这套顶级架构的复现与排坑。

---

## 概述

本仓库通过 npm 发布包（`@anthropic-ai/claude-code`）内附带的 source map（`cli.js.map`）还原的 TypeScript 源码，版本为 `2.1.88`。

- **还原文件数**：4756 个（含 1884 个 `.ts`/`.tsx` 源文件）
- **核心逻辑**：提取 `cli.js.map` 中的 `sourcesContent` 字段。

## 目录结构

```text
restored-src/src/
├── main.tsx              # CLI 入口
├── tools/                # 工具实现（Bash、FileEdit、Grep、MCP 等 30+ 个）
├── commands/             # 命令实现（commit、review、config 等 40+ 个）
├── services/             # API、MCP、分析等服务
├── utils/                # 工具函数（git、model、auth、env 等）
├── context/              # React Context
├── coordinator/          # 多 Agent 协调模式
├── assistant/            # 助手模式（KAIROS）
├── buddy/                # AI 伴侣 UI
├── remote/               # 远程会话
├── plugins/              # 插件系统
├── skills/               # 技能系统
├── voice/                # 语音交互
└── vim/                  # Vim 模式
```

## 🤝 抱团排坑与纯净交流

这波 Claude Code 源码泄露，直接让国内大厂的 AI Agent 强行进步了至少半年。

但对咱们普通开发者来说，还没人能轻易把它完美跑通。为了不一个人闭门造车，我拉了个**纯粹的AI交流群**：

- **状态**：目前还没人完全跑通，大家正抱团试错。
- **调性**：**坚决不卖课、无商业化。** 拒绝浮夸与焦虑，主打务实和克制。
- **目标**：前期死磕源码，后期聊 AIGC 真实落地经验。

如果你也想找个干净的地方聊技术，欢迎一起慢慢折腾。

**进群方式：** 添加微信：Yxz_Rainy *(请备注：Claude)*

---

## 声明

- 源码版权归 [Anthropic](https://www.anthropic.com/) 所有
- 本仓库仅用于技术研究与学习，请勿用于商业用途
- 如有侵权，请联系删除
