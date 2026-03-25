# 常用命令速查

## Claude Code

| 命令 | 说明 |
|------|------|
| `claude --dangerously-skip-permissions` | 跳过所有权限确认启动（危险，仅用于可信环境） |
| `claude --model <model-id>` | 指定模型启动 |
| `claude --resume` | 恢复上次对话 |
| `claude --continue` | 继续最近的对话 |
| `/help` | 查看帮助 |
| `/reload-plugins` | 重新加载插件 |
| `/compact` | 压缩对话上下文 |
| `/clear` | 清空对话 |
| `/cost` | 查看当前会话花费 |

## 插件管理

| 命令 | 说明 |
|------|------|
| `/install <plugin>@<marketplace>` | 安装插件 |
| `/plugins` | 查看已安装插件 |
| `/reload-plugins` | 重新加载插件 |

## Git 相关

| 命令 | 说明 |
|------|------|
| `/commit` | 让 Claude 生成 commit |
| `/code-review` | 自动审查 PR |
