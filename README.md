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
| [code-review](skills/code-review/SKILL.md) | `/code-review` | 多代理并行审查 PR，置信度评分过滤误报 |
| [code-simplifier](skills/code-simplifier/SKILL.md) | `/simplify` | 简化代码，提升清晰度和可维护性 |

### 工具与插件

| 项目 | 说明 |
|------|------|
| [claude-code-hub](skills/claude-code-hub/README.md) | AI API 代理中转平台（Next.js + Hono + PG + Redis） |
| [claude-hud](skills/claude-hud/README.md) | Claude Code 状态栏插件（上下文/工具/代理/任务实时显示） |

## 常用命令

速查表 → [commands/README.md](commands/README.md)

## 目录结构

```
├── skills/
│   ├── superpowers/           # Superpowers 插件技能速查
│   │   └── README.md
│   ├── code-review/           # PR 审查技能
│   │   ├── README.md
│   │   └── SKILL.md
│   ├── code-simplifier/       # 代码简化技能
│   │   ├── README.md
│   │   └── SKILL.md
│   ├── claude-code-hub/       # API 代理中转平台
│   │   └── README.md
│   └── claude-hud/            # 状态栏插件
│       └── README.md
├── commands/                   # 常用命令
│   └── README.md
└── README.md                   # 本文件（总索引）
```

## 如何添加新内容

- **新技能**：在 `skills/` 下建文件夹 → 创建 `SKILL.md`（含 YAML frontmatter）+ `README.md`（速查）→ 更新本索引
- **新命令**：直接编辑 `commands/README.md`
- **新插件**：在 `skills/` 下建插件同名文件夹 → 创建 `README.md` 速查 → 更新本索引
