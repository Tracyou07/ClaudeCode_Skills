# 论文阅读与审稿工具

Claude Code 中用于论文阅读、分析和审稿的 Skill 合集。

## 安装来源

```bash
# paper-glance 和 ai-review-skill 来自 PPW 生态
npx skills add <source> --skill paper-glance -g --agent claude-code
npx skills add <source> --skill ai-review-skill -g --agent claude-code
npx skills add <source> --skill get-paper -g --agent claude-code
```

## 包含的 Skill

### 1. Paper Glance — 论文全能处理

- **触发方式**: 上传论文 PDF、粘贴文本/摘要、提到"论文"/"paper"/"文献"/"arxiv"时自动触发
- **功能菜单**:

| # | 功能 | 说明 |
|---|------|------|
| 1 | 深度分析报告 | 方法、实验、创新点的完整学术解读 |
| 2 | 思维导图 | Mermaid 思维导图或流程图，即时渲染 |
| 3 | 审稿意见 | Summary / Strengths / Weaknesses / Questions |
| 4 | 宣传脚本 | 社交媒体推文、公众号摘要、演讲介绍 |
| 5 | 播客音频 | 单人解说或双人对话脚本，可生成 MP3 |
| 0 | 全部 | 按 1-5 顺序依次生成 |

### 2. AI Review Skill — 结构化审稿

- **触发方式**: 输入"审稿"、"论文审稿"、"review my paper"
- **支持格式**: LaTeX (`.tex`)、PDF (`.pdf`)、Word (`.docx`/`.doc`)
- **语言检测**: 自动识别中英文，输出语言与论文匹配
- **四种模式**:

| 模式 | 触发信号 | 说明 |
|------|---------|------|
| SoT（默认） | 无需指定 | Skeleton-of-Thought，多阶段链式推理 |
| Pure | "简洁提示"/"minimal" | 无推理脚手架的精简审稿 |
| Few-Shot | "用例子"/"with example" | 附带 ResNet 审稿示例 |
| VLM-Specific | "看图审稿"/"with figures" | 视觉模型模式，可分析图表排版 |

### 3. Get Paper — Google Scholar 搜索

- **触发方式**: `/get-paper <关键词>` 或 "帮我在谷歌学术搜索论文"
- **依赖**: Chrome DevTools MCP（需要本地 Chrome 浏览器）
- **功能**: 自动搜索 Google Scholar → 展示结果 → 用户选择 → 获取 BibTeX
- **输出**: BibTeX 引用条目

## 使用场景

| 场景 | 推荐 Skill |
|------|-----------|
| 快速了解一篇论文 | Paper Glance |
| 正式审稿/写 review | AI Review Skill |
| 查找论文并获取引用 | Get Paper |
| 生成论文宣传内容 | Paper Glance (功能 4/5) |

## 注意事项

- Paper Glance 和 AI Review Skill 功能有重叠（审稿），前者偏快速概览，后者更严谨深入
- Get Paper 依赖 Chrome DevTools MCP，需确保 Chrome 已打开并配置了 MCP
- PDF 解析质量取决于 PDF 内容结构，扫描版 PDF 效果较差
