# Superpowers 插件技能速查

插件版本：5.0.5 | 安装：`/install superpowers@claude-plugins-official`

## 核心工作流

| 技能 | 命令 | 说明 |
|------|------|------|
| brainstorming | `/brainstorming` | 在创建功能、构建组件前探索需求和设计 |
| writing-plans | `/writing-plans` | 基于需求规格制定多步骤实施计划 |
| executing-plans | `/executing-plans` | 在独立会话中按计划执行，带审查检查点 |
| test-driven-development | `/test-driven-development` | 先写测试，再写实现（RED-GREEN-REFACTOR） |

## 开发流程

| 技能 | 命令 | 说明 |
|------|------|------|
| using-git-worktrees | `/using-git-worktrees` | 创建隔离 git worktree 进行功能开发 |
| subagent-driven-development | `/subagent-driven-development` | 用子代理并行执行独立任务 |
| dispatching-parallel-agents | `/dispatching-parallel-agents` | 面对 2+ 个独立任务时并行分派代理 |

## 质量保证

| 技能 | 命令 | 说明 |
|------|------|------|
| systematic-debugging | `/systematic-debugging` | 系统化分析 bug，先诊断再修复 |
| verification-before-completion | `/verification-before-completion` | 声称完成前必须运行验证命令 |
| requesting-code-review | `/requesting-code-review` | 完成任务后请求代码审查 |
| receiving-code-review | `/receiving-code-review` | 严谨处理审查反馈，不盲目同意 |

## 收尾

| 技能 | 命令 | 说明 |
|------|------|------|
| finishing-a-development-branch | `/finishing-a-development-branch` | 引导合并、PR 或清理分支 |
| writing-skills | `/writing-skills` | 创建、编辑和验证自定义技能（TDD 方式） |

## 推荐流程

```
/brainstorming        →  明确需求和设计
/writing-plans        →  制定实施计划
/using-git-worktrees  →  创建隔离分支
/test-driven-development → 先写测试
/executing-plans      →  按计划实现
/systematic-debugging →  调试（如需要）
/verification-before-completion → 验证结果
/requesting-code-review → 请求审查
/finishing-a-development-branch → 合并或 PR
```

## 辅助命令

| 命令 | 说明 |
|------|------|
| `/brainstorm` | brainstorming 的快捷命令 |
| `/write-plan` | writing-plans 的快捷命令 |
| `/execute-plan` | executing-plans 的快捷命令 |
