# Claude Code Hub

智能 AI API 代理中转服务平台，面向团队的多供应商统一接入、弹性调度与精细化运营中心。

## 项目信息

- **仓库**: https://github.com/ding113/claude-code-hub
- **技术栈**: Next.js 16 + Hono + PostgreSQL + Redis + Drizzle ORM
- **包管理器**: Bun (1.3+)
- **测试框架**: Vitest + happy-dom
- **UI**: React 19 + shadcn/ui + Tailwind CSS + Recharts
- **i18n**: next-intl（zh-CN, zh-TW, en, ja, ru）

## 核心功能

- 智能负载均衡（权重 + 优先级 + 熔断 + 故障转移）
- 多供应商管理（Claude、Codex、Gemini、OpenAI Compatible）
- 多维限流（RPM、金额、并发 Session，Redis Lua 原子操作）
- 自动化 OpenAPI 文档（39 个 REST 端点，Swagger + Scalar UI）
- 实时监控仪表盘（Session、消耗排行、决策链、代理状态）
- Session 管理（5 分钟上下文缓存 + 决策链记录）

## 核心架构

```
Request -> GuardPipeline -> [auth -> sensitive -> client -> model -> ...] ->
           ProxyForwarder -> ProxyResponseHandler -> Response
```

- 代理端点: `/v1/messages`, `/v1/chat/completions`, `/v1/responses`
- 管理 API: `/api/actions/{module}/{action}`

## 常用命令

```bash
bun install               # 安装依赖
bun run dev               # 开发服务器 (端口 13500)
bun run build             # 生产构建
bun run test              # 运行测试
bun run typecheck         # TypeScript 检查 (tsgo)
bun run lint              # Biome 检查
bun run db:generate       # 生成 Drizzle 迁移
bun run db:migrate        # 执行迁移
```

## 关键规则

- PR 目标分支: `dev`
- 代码中禁止使用 Emoji
- 新功能测试覆盖率 >= 80%
- 所有用户可见字符串必须使用 i18n
- 数据库迁移必须通过 Drizzle 生成，禁止手写 SQL

## 部署

支持 Docker Compose 一键部署，需要 PostgreSQL + Redis。

## 项目文件

- 详细开发规范 → [CLAUDE.md](../../claude-code-hub/CLAUDE.md)
- 完整文档 → [README.md](../../claude-code-hub/README.md)
