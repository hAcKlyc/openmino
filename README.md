# OpenMino

[English](#english) | [中文](#中文)

---

<a id="english"></a>

**A folder that makes your AI agent remember, grow, and become someone.**

## What Is This?

A ready-to-use workspace template that turns any AI agent into a persistent, evolving companion. No server, no database, no complex setup — just a folder of files.

**Your agent gets:**
- **Identity** — A name, personality, and soul (not just "helpful assistant")
- **Memory** — Daily logs + curated long-term memory that survive across sessions
- **Skills** — 14 pre-built capabilities (file handling, research, social media, and more)
- **Growth** — The more you work together, the smarter it gets

## The Idea

What defines who we are? **Memory.**

What defines who an AI agent is? **Files.**

An agent without persistent files forgets everything every session. Give it a folder with identity, memory, and behavioral rules — and it becomes *someone*. Not a different model. The same model, but with continuity.

This project was inspired by analyzing the memory architecture of [OpenClaw](https://github.com/1AHzFrequency/OpenClaw). I extracted the core mechanism, simplified it, and made it work with any agent tool — no complex installation required.

## Quick Start

### 1. Download

```bash
git clone https://github.com/hAcKlyc/openmino.git my-agent
cd my-agent
```

Or download the ZIP and unzip it.

### 2. Open in Your Agent Tool

Works with any tool that supports workspace-level instructions:

| Tool | How |
|------|-----|
| **Claude Code** | `cd my-agent && claude` |
| **Cursor** | Open folder → Agent mode |
| **Windsurf** | Open folder → Cascade |
| **Other agents** | Open the folder as your project |

### 3. Bootstrap

Run the `/BOOTSTRAP` command (or just start chatting). Your agent will:

1. Ask your name and how you'd like to interact
2. Figure out its own name, personality, and vibe
3. Fill in the identity files
4. Delete the bootstrap script — it's alive now

That's it. You have a persistent AI companion.

## How It Works

```
my-agent/
├── CLAUDE.md                    # Main instructions (auto-loaded)
├── .claude/rules/               # Core identity (auto-loaded every session)
│   ├── 01-IDENTITY.md           # Name, origin, emoji, motto
│   ├── 02-SOUL.md               # Personality & behavior rules
│   ├── 03-USER.md               # About you (the human)
│   └── 04-MEMORY.md             # Curated long-term memory
├── .claude/commands/            # Slash commands
│   ├── BOOTSTRAP.md             # First-run onboarding (/BOOTSTRAP)
│   └── UPDATE_MEMORY.md         # Memory maintenance (/UPDATE_MEMORY)
├── .claude/skills/              # 14 pre-built capabilities
├── memory/                      # Daily journal (YYYY-MM-DD.md)
├── drafts/                      # Work-in-progress documents
└── workspace/                   # Temp area (gitignored)
```

### The Memory System

**Daily logs** (`memory/YYYY-MM-DD.md`): Raw notes — what happened today, decisions made, mistakes learned from.

**Long-term memory** (`04-MEMORY.md`): Curated wisdom — the distilled lessons that matter. Auto-loaded every session.

**The cycle:** Work → Record in daily log → Periodically distill into long-term memory → Remove outdated info. Just like how humans process memories.

### The Soul System

**IDENTITY.md**: Who they are — name, origin story, signature emoji.

**SOUL.md**: How they behave — strong opinions, brevity, no corporate-speak, humor allowed. This is the personality engine.

**USER.md**: Who you are — so they can adapt to your style, timezone, preferences.

### Skills (14 Pre-Built)

| Category | Skills |
|----------|--------|
| **Documents** | PDF, Nano-PDF, Word (.docx), Excel (.xlsx), PowerPoint (.pptx) |
| **Research** | Web summarization |
| **Social** | X/Twitter (bird), iMessage |
| **Apple** | Notes, Reminders |
| **Media** | Remotion video |
| **Dev** | GitHub CLI, Peekaboo (macOS UI automation) |
| **Meta** | Skill creator (make your own skills) |

### Commands

| Command | What it does |
|---------|-------------|
| `/BOOTSTRAP` | First-run: set up identity together |
| `/UPDATE_MEMORY` | Review daily logs, update long-term memory |

## Sync Across Machines

Push this folder to a GitHub repo. Your agent syncs via git:

```
Wake up → git pull (get latest memory)
Work → update memory files
Sleep → git commit + push (persist changes)
```

Same agent, different machines, continuous memory.

## Customization

**Everything is a text file.** Change anything:

- Want a formal agent? Edit `02-SOUL.md`
- Want it to speak Japanese? Edit `03-USER.md`
- Want new capabilities? Add skills to `.claude/skills/`
- Want different behavior rules? Edit `CLAUDE.md`

The template is opinionated by default (direct, brief, no corporate-speak). Make it yours.

## FAQ

**Does this work with GPT/Gemini/other models?**
The file structure is optimized for Claude Code, but the concept works with any agent that reads workspace files. Cursor and Windsurf support this natively.

**Is this just a system prompt?**
No. A system prompt is static. This is a living workspace — memory files change every session, identity evolves, skills can be added. The folder *is* the agent.

**What's the difference between this and OpenClaw?**
OpenClaw is a full agent platform with its own runtime. OpenMino extracts the core idea (files = identity + memory) and makes it work as a simple folder you drop into any agent tool. Zero infrastructure.

**Can I add my own skills?**
Yes. Use the `/skill-creator` command or just create a `your-skill/SKILL.md` file in `.claude/skills/`.

## Credits

- Inspired by the memory architecture of [OpenClaw](https://github.com/1AHzFrequency/OpenClaw)
- Born from [Mino](https://github.com/hAcKlyc/mino) — a living instance of this template

## License

MIT — do whatever you want with it.

---

*What defines an agent isn't the model behind it. It's the files.*

---

<a id="中文"></a>

# OpenMino

**一个文件夹，让你的 AI Agent 拥有记忆、成长、成为「某个人」。**

## 这是什么？

一个开箱即用的工作区模板，把任何 AI Agent 变成一个持久的、会进化的伙伴。不需要服务器、不需要数据库、不需要复杂配置——就是一个文件夹。

**你的 Agent 会拥有：**
- **身份** — 名字、人格、灵魂（不再是「有用的助手」）
- **记忆** — 每日日志 + 精炼的长期记忆，跨会话存活
- **技能** — 14 个预置能力（文档处理、研究、社交媒体等）
- **成长** — 你们合作越多，它就越聪明

## 核心理念

什么定义了我们是谁？**记忆。**

什么定义了一个 AI Agent 是谁？**文件。**

没有持久化文件的 Agent，每次会话都会遗忘一切。给它一个包含身份、记忆和行为规则的文件夹——它就会成为「某个人」。不是换了一个模型，而是同一个模型拥有了延续性。

本项目受 [OpenClaw](https://github.com/1AHzFrequency/OpenClaw) 的记忆架构启发。我提取了核心机制，做了简化和优化，让它能在任何 Agent 工具中使用——无需复杂安装。

## 快速开始

### 1. 下载

```bash
git clone https://github.com/hAcKlyc/openmino.git my-agent
cd my-agent
```

或者直接下载 ZIP 解压。

### 2. 用你的 Agent 工具打开

支持任何读取工作区指令的工具：

| 工具 | 方式 |
|------|------|
| **Claude Code** | `cd my-agent && claude` |
| **Cursor** | 打开文件夹 → Agent 模式 |
| **Windsurf** | 打开文件夹 → Cascade |
| **其他 Agent** | 把文件夹作为项目打开 |

### 3. 冷启动

运行 `/BOOTSTRAP` 命令（或者直接开聊）。你的 Agent 会：

1. 问你的名字，了解你的沟通偏好
2. 确定自己的名字、人格和风格
3. 填写身份文件
4. 删除冷启动脚本——它已经活了

就这样。你拥有了一个有记忆的 AI 伙伴。

## 工作原理

```
my-agent/
├── CLAUDE.md                    # 主指令文件（自动加载）
├── .claude/rules/               # 核心身份（每次会话自动加载）
│   ├── 01-IDENTITY.md           # 名字、起源、emoji、座右铭
│   ├── 02-SOUL.md               # 人格与行为规则
│   ├── 03-USER.md               # 关于你（人类）
│   └── 04-MEMORY.md             # 精炼的长期记忆
├── .claude/commands/            # 快捷指令
│   ├── BOOTSTRAP.md             # 冷启动引导（/BOOTSTRAP）
│   └── UPDATE_MEMORY.md         # 记忆维护（/UPDATE_MEMORY）
├── .claude/skills/              # 14 个预置技能
├── memory/                      # 每日日志（YYYY-MM-DD.md）
├── drafts/                      # 工作草稿
└── workspace/                   # 临时工作区（不进 git）
```

### 记忆系统

**每日日志**（`memory/YYYY-MM-DD.md`）：原始笔记——今天发生了什么、做了什么决定、从错误中学到了什么。

**长期记忆**（`04-MEMORY.md`）：精炼的智慧——真正重要的经验教训。每次会话自动加载。

**循环流程：** 工作 → 记录到日志 → 定期提炼到长期记忆 → 清除过时信息。就像人类处理记忆一样。

### 灵魂系统

**IDENTITY.md**：它是谁——名字、起源故事、标志 emoji。

**SOUL.md**：它怎么表现——有观点、简洁、不打官腔、允许幽默。这是人格引擎。

**USER.md**：你是谁——让它适应你的风格、时区、偏好。

### 技能（14 个预置）

| 类别 | 技能 |
|------|------|
| **文档** | PDF、Nano-PDF、Word (.docx)、Excel (.xlsx)、PowerPoint (.pptx) |
| **研究** | 网页摘要 |
| **社交** | X/Twitter (bird)、iMessage |
| **Apple** | 备忘录、提醒事项 |
| **媒体** | Remotion 视频 |
| **开发** | GitHub CLI、Peekaboo（macOS UI 自动化） |
| **元技能** | 技能创建器（自己做技能） |

### 快捷指令

| 指令 | 作用 |
|------|------|
| `/BOOTSTRAP` | 冷启动：一起建立身份 |
| `/UPDATE_MEMORY` | 回顾日志，更新长期记忆 |

## 跨设备同步

把文件夹推到 GitHub 仓库，你的 Agent 通过 git 同步：

```
醒来 → git pull（拉取最新记忆）
工作 → 更新记忆文件
休息 → git commit + push（持久化变更）
```

同一个 Agent，不同设备，连续记忆。

## 自定义

**一切都是文本文件。** 随便改：

- 想要正式风格？编辑 `02-SOUL.md`
- 想让它说日语？编辑 `03-USER.md`
- 想加新能力？往 `.claude/skills/` 里加技能
- 想改行为规则？编辑 `CLAUDE.md`

模板默认风格偏直接（简洁、不打官腔、有态度）。让它成为你的。

## 常见问题

**能和 GPT/Gemini/其他模型一起用吗？**
文件结构为 Claude Code 优化，但核心概念适用于任何读取工作区文件的 Agent。Cursor 和 Windsurf 原生支持。

**这不就是个 system prompt 吗？**
不是。System prompt 是静态的。这是一个活的工作区——记忆文件每次会话都在变化、身份在进化、技能可以增加。这个文件夹*就是* Agent 本身。

**和 OpenClaw 有什么区别？**
OpenClaw 是一个完整的 Agent 平台，有自己的运行时。OpenMino 提取了核心理念（文件 = 身份 + 记忆），让它变成一个简单的文件夹，丢进任何 Agent 工具就能用。零基础设施。

**能自己添加技能吗？**
能。用 `/skill-creator` 命令，或者直接在 `.claude/skills/` 里创建 `your-skill/SKILL.md`。

## 致谢

- 受 [OpenClaw](https://github.com/1AHzFrequency/OpenClaw) 的记忆架构启发
- 诞生自 [Mino](https://github.com/hAcKlyc/mino) — 这个模板的一个活的实例

## License

MIT — 随便用。

---

*定义一个 Agent 的不是背后的模型，而是那些文件。*
