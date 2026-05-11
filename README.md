# Claude Code Skills & Commands

个人维护的 Claude Code 技能和常用命令合集，方便快速翻阅。

## 技能索引（按功能分类）

### 开发工作流

| 技能 | 命令/触发 | 说明 | 速查 |
|------|----------|------|------|
| Superpowers | 多个子技能 | 结构化开发全流程（规划→编码→测试→审查→收尾） | [详情](skills/development/superpowers/README.md) |
| code-review | `/code-review` | 多代理并行 PR 审查，带置信度评分过滤 | [详情](skills/development/code-review/SKILL.md) |
| code-simplifier | `/simplify` | 自动简化最近修改的代码，不改变功能 | [详情](skills/development/code-simplifier/SKILL.md) |

### 任务规划与管理

| 技能 | 命令/触发 | 说明 | 速查 |
|------|----------|------|------|
| planning-with-files | `/planning-with-files-zh` | Manus 风格三文件系统（task_plan / findings / progress） | [详情](skills/planning/planning-with-files/README.md) |

### 论文阅读与审稿

| 技能 | 命令/触发 | 说明 | 速查 |
|------|----------|------|------|
| Paper Glance | 上传论文/提到"论文" | 全能处理（分析、思维导图、审稿、宣传、播客） | [详情](skills/research/paper-review/README.md) |
| AI Review Skill | "审稿"/"review my paper" | 结构化审稿，SoT/Pure/Few-Shot/VLM 四种模式 | [详情](skills/research/paper-review/README.md) |
| Get Paper | `/get-paper <关键词>` | Google Scholar 搜索 + BibTeX 获取 | [详情](skills/research/paper-review/README.md) |

### 科研项目管理

| 技能 | 精确触发词 | 说明 | 速查 |
|------|-----------|------|------|
| 进度追踪 | `科研启动` | 多 Agent 并行 + Git 管理 + PROGRESS.md | [详情](skills/research/research-management/README.md) |
| 任务执行 | `科研启动-执行` | 最小完整方案 + 链路检查 | [详情](skills/research/research-management/README.md) |
| 算法检查 | `科研启动-检查` | 5 Agent 分工审查 + ISSUES.md | [详情](skills/research/research-management/README.md) |

### 工具与插件

| 项目 | 说明 | 速查 |
|------|------|------|
| claude-code-hub | AI API 代理中转平台，多供应商统一接入 | [详情](skills/tools/claude-code-hub/README.md) |
| claude-hud | 状态栏插件，实时显示上下文/工具/代理/任务 | [详情](skills/tools/claude-hud/README.md) |
| using-codex | 在 Claude Code 中使用 Codex CLI 获取第二意见 | [详情](skills/tools/using-codex/README.md) |

## 常用命令

速查表 → [commands/README.md](commands/README.md)

## 目录结构

```text
├── skills/
│   ├── development/               # 开发工作流
│   │   ├── superpowers/
│   │   ├── code-review/
│   │   └── code-simplifier/
│   ├── planning/                  # 任务规划
│   │   └── planning-with-files/
│   ├── research/                  # 科研相关
│   │   ├── paper-review/
│   │   └── research-management/
│   └── tools/                     # 工具与插件
│       ├── claude-code-hub/
│       ├── claude-hud/
│       └── using-codex/
├── commands/                      # 常用命令速查
└── README.md                      # 本文件（总索引）
```

## 如何添加新内容

- **新技能**：在对应分类目录下建文件夹 → 创建 `SKILL.md` + `README.md` → 更新本索引
- **新命令**：直接编辑 `commands/README.md`
- **新插件**：在 `skills/tools/` 下建同名文件夹 → 创建 `README.md` → 更新本索引
