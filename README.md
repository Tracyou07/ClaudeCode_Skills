# Claude Code Skills & Commands

个人维护的 Claude Code 技能和常用命令合集，方便快速翻阅。

## 插件技能

### Superpowers（结构化开发工作流）

完整速查 → [skills/superpowers/README.md](skills/superpowers/README.md)

| 类别 | 技能 |
|------|------|
| 核心工作流 | `brainstorming` · `writing-plans` · `executing-plans` · `test-driven-development` |
| 开发流程 | `using-git-worktrees` · `subagent-driven-development` · `dispatching-parallel-agents` |
| 质量保证 | `systematic-debugging` · `verification-before-completion` · `requesting-code-review` · `receiving-code-review` |
| 收尾 | `finishing-a-development-branch` · `writing-skills` |

### 独立技能

| 技能 | 命令 | 说明 |
|------|------|------|
| [code-review](skills/code-review/SKILL.md) | `/code-review` | 多代理并行 PR 审查，带置信度评分过滤 |
| [code-simplifier](skills/code-simplifier/SKILL.md) | `/simplify` | 自动简化和优化最近修改的代码，提升清晰度和可维护性，不改变功能 |
| [planning-with-files](skills/planning-with-files/README.md) | `/plan` | Manus 风格的文件规划系统，用持久化 Markdown 文件替代易失的上下文记忆 |

### 工具与插件

| 项目 | 说明 |
|------|------|
| [claude-code-hub](skills/claude-code-hub/README.md) | 智能 AI API 代理中转服务平台，面向团队的多供应商统一接入、弹性调度与精细化运营中心 |
| [claude-hud](skills/claude-hud/README.md) | Claude Code 插件，在输入框下方实时显示会话状态：上下文用量、工具活动、代理追踪、任务进度 |
| [using-codex](skills/using-codex/README.md) | 在 Claude Code 中使用 OpenAI Codex CLI 作为辅助工具，获取第二意见或委托子任务 |

## 常用命令

速查表 → [commands/README.md](commands/README.md)

## 目录结构

```text
├── skills/
│   ├── superpowers/           # Superpowers 插件技能速查
│   │   └── README.md
│   ├── code-review/           # PR 审查技能
│   │   ├── README.md
│   │   └── SKILL.md
│   ├── code-simplifier/       # 代码简化技能
│   │   ├── README.md
│   │   └── SKILL.md
│   ├── planning-with-files/   # 文件规划系统技能
│   │   └── README.md
│   ├── claude-code-hub/       # AI API 代理中转平台
│   │   └── README.md
│   ├── claude-hud/            # 状态栏插件
│   │   └── README.md
│   └── using-codex/           # Codex CLI 辅助工具
│       └── README.md
├── commands/                  # 常用命令
│   └── README.md
└── README.md                  # 本文件（总索引）
```

## 如何添加新内容

- **新技能**：在 `skills/` 下建文件夹 → 创建 `SKILL.md`（含 YAML frontmatter）+ `README.md`（速查）→ 更新本索引
- **新命令**：直接编辑 `commands/README.md`
- **新插件**：在 `skills/` 下建插件同名文件夹 → 创建 `README.md` 速查 → 更新本索引
