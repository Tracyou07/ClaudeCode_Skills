# Using Codex in Claude Code

在 Claude Code 中使用 OpenAI Codex CLI 作为辅助工具，获取第二意见或委托子任务。

## 项目信息

- **插件来源**: openai-codex (Claude Code 官方插件市场)
- **Codex CLI**: `@openai/codex`
- **当前版本**: 0.107.0

## 安装

### 1. 安装 Codex CLI

```bash
npm install -g @openai/codex
```

### 2. 登录认证

在 Claude Code 中运行：

```
! codex login
```

支持 ChatGPT 账号登录，认证后即可使用。

### 3. 验证安装

```
/codex:setup
```

显示 Node、npm、Codex CLI、认证状态等信息。

## 可用命令

| 命令 | 用途 | 使用场景 |
|------|------|---------|
| `/codex:setup` | 检查 Codex 是否就绪 | 首次使用或排查问题 |
| `/codex:rescue` | 委托任务给 Codex 子代理 | 卡住时、需要第二意见、深度调查 |

### 内部 Skill（自动调用，无需手动触发）

| Skill | 作用 |
|-------|------|
| `codex:codex-cli-runtime` | 管理 Codex 运行时的启动和通信 |
| `codex:gpt-5-4-prompting` | 为 Codex/GPT 编写优化提示 |
| `codex:codex-result-handling` | 处理和呈现 Codex 返回的结果 |

## 使用场景

### 适合委托给 Codex 的情况

- **卡住了** — Claude 尝试多次仍无法解决，让 Codex 提供不同视角
- **需要第二意见** — 对实现方案不确定，获取独立验证
- **深度根因分析** — 复杂 bug 需要更深入的调查
- **大型编码任务** — 将独立的子任务委托出去，并行推进

### 不适合的情况

- 简单问答或单文件编辑
- 需要访问 Claude Code 特有工具（MCP、插件等）的任务
- Codex 运行在受限沙箱中，无法访问网络或外部服务

## 工作原理

```
用户 → Claude Code → /codex:rescue → Codex CLI (GPT) → 结果返回 Claude
```

1. Claude Code 将任务描述发送给 Codex CLI
2. Codex 在本地沙箱中执行（可读写文件、运行命令）
3. 结果返回 Claude Code，由 Claude 审查后呈现给用户

## Review Gate（可选）

启用后，Claude 在结束前会自动请求 Codex 审查代码：

```
/codex:setup --enable-review-gate
```

## 注意事项

- Codex 使用 OpenAI 的模型，需要有效的 OpenAI/ChatGPT 账号
- Codex 在沙箱环境运行，部分命令可能被拒绝
- 文件写入权限受限，复杂写入操作可能需要 Claude 接手完成
- Codex 的上下文独立于 Claude，需要在提示中提供足够背景
