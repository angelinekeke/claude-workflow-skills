---
name: daily-log
description: Write a daily work log documenting everything done today, including completed tasks, problems encountered, solutions found, and reflections for improvement. Use this skill when the user wants to record and summarize the day's work with Claude Code.
---

# 写每日工作记录

在会话结束时，生成一份完整的当天工作记录文档。

## 第一步：收集今天的工作内容

通过以下方式收集本次会话及今天的全部工作：
- 回顾对话历史，梳理做了哪些事
- 如果是 git 仓库，运行 `git log --since="today" --oneline` 查看今天的提交
- 检查 `git diff HEAD~5..HEAD --stat` 了解文件改动范围

## 第二步：整理踩坑与解决方案

从对话历史中识别：
- 遇到的报错、失败的尝试、走过的弯路
- 最终采用的解决方案
- 用表格形式呈现（问题 | 原因 | 解决方案）

## 第三步：提炼思考与改进

针对今天的工作，思考：
- 哪些做法值得以后复用？
- 哪些做法下次可以更高效？
- 有没有发现新的工具或技巧？
- 有没有适合做成 skill 的重复性流程？

## 第四步：写入文档

将文档写入以下路径（按优先级）：
1. 如果存在 `D:/steam-game/claude/` 目录，写入该目录
2. 否则写入项目根目录的 `docs/` 目录
3. 都不存在则写入当前目录

文件名格式：`YYYY-MM-DD-daily-log.md`（使用今天的日期）

文档结构如下：

```markdown
# 每日工作记录 YYYY-MM-DD

---

## ✅ 今天完成的事
（按时间或主题分组，每项说明做了什么、为什么做、结果如何）

## 🔥 踩坑与解决方案

| 问题 | 原因 | 解决方案 |
|------|------|---------|
| ...  | ...  | ...     |

## 💡 思考与改进
（总结经验、更好的做法、值得沉淀的模式）

## 📋 后续待办
（今天没做完的、受今天启发想做的）

---
*记录人：花哥 | YYYY-MM-DD*
```

用中文书写。

## 第五步：确认

告知用户文档保存路径，并列出「后续待办」让用户确认。

---

## 注意事项

- 记录要有实质内容，不要写空话套话
- 踩坑记录要写清楚**原因**，光写「失败了」没用
- 思考部分是最有价值的，认真写，不要敷衍
- 如果今天工作量很大，按主题分组，不要一股脑全堆在一起
