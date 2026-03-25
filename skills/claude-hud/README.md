# Claude HUD

Claude Code 插件，在输入框下方实时显示会话状态：上下文用量、工具活动、代理追踪、任务进度。

## 项目信息

- **仓库**: https://github.com/jarrodwatts/claude-hud
- **类型**: Claude Code 插件（statusLine）
- **技术栈**: TypeScript 5 + Node.js 18+ / Bun
- **构建目标**: ES2022, NodeNext modules

## 安装

```
/plugin marketplace add jarrodwatts/claude-hud
/plugin install claude-hud
/claude-hud:setup
```

## 功能一览

| 模块 | 显示内容 |
|------|---------|
| 项目行 | 模型名 + 项目路径 + Git 分支/状态 |
| 上下文条 | 上下文窗口使用百分比（绿/黄/红） |
| 用量条 | 5 小时/7 天订阅用量 |
| 工具行 | 当前执行的工具名和状态（opt-in） |
| 代理行 | 运行中的子代理及描述（opt-in） |
| 任务行 | Todo 完成进度（opt-in） |
| 环境行 | CLAUDE.md / MCP / Hooks 计数（opt-in） |

## 数据流

```
Claude Code → stdin JSON → 解析 → 渲染多行 → stdout → Claude Code 显示
           ↘ transcript_path → 解析 JSONL → 工具/代理/任务
```

每 ~300ms 调用一次，stdin 提供模型和上下文数据，transcript JSONL 提供工具/代理/任务数据。

## 核心文件结构

```
src/
├── index.ts           # 入口
├── stdin.ts           # 解析 Claude JSON 输入
├── transcript.ts      # 解析 transcript JSONL
├── config.ts          # 用户配置加载
├── git.ts             # Git 状态
└── render/            # 渲染各行输出
```

## 常用命令

```bash
npm ci                # 安装依赖
npm run build         # 构建 TypeScript 到 dist/
```

## 插件命令

- `/claude-hud:setup` — 配置 statusLine 到 settings.json
- `/claude-hud:configure` — 调整 HUD 显示选项（布局、预设、显示元素）

## 上下文阈值

| 阈值 | 颜色 | 含义 |
|------|------|------|
| <70% | 绿色 | 正常 |
| 70-85% | 黄色 | 警告 |
| >85% | 红色 | 显示 token 明细 |

## 项目文件

- 详细开发规范 → [CLAUDE.md](../../claude-hud/CLAUDE.md)
- 完整文档 → [README.md](../../claude-hud/README.md)
