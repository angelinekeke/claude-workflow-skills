---
name: progress
description: Write a progress document summarizing what was completed, what remains, known issues, and next steps for the current session. Use this skill at the end of a work session or when the user asks to save progress.
---

# 保存会话进度

在会话结束时写一份进度文档，供下次会话使用。

## 第一步：收集本次会话的改动

通过以下方式收集本次会话的变更：
- 如果是 git 仓库，运行 `git diff HEAD` 或 `git status`
- 回顾对话历史中写入、编辑或讨论过的文件
- 记录实现的功能、修复的 bug 或做出的决策

## 第二步：确认剩余工作

根据原始任务和已完成内容，整理：
- 已开始但未完成的任务
- 计划中但尚未开始的任务
- 发现的任何阻塞问题或未解决的 bug

## 第三步：写进度文档

将 Markdown 文件写入 `docs/progress-YYYY-MM-DD.md`（使用今天的日期）。

文档必须包含以下章节：

```markdown
# 进度记录 YYYY-MM-DD

## ✅ 本次完成
- ...

## 🔄 进行中 / 未完成
- ...

## ⚠️ 已知问题
- ...

## 📋 下一步
1. ...
2. ...

## 🗒️ 备注
（可选，记录重要决策、环境注意事项等）
```

默认用中文书写。

## 第四步：确认

汇报进度文档保存的路径，并简要列出「下一步」内容，让用户在关闭会话前能快速确认。

---

## 注意事项

- 如果 `docs/` 目录不存在，先创建它
- 每条要点保持简洁，一行一项
- 「下一步」是最重要的章节：写得具体可执行，让下次会话能立刻开始干活
- 如果有未解决的错误或阻塞问题，在「已知问题」中清楚记录
