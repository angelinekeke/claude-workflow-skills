---
name: continue
description: Resume development from the last session by reading progress docs and summarizing what was done, what remains, and what to work on next. Use this skill when the user wants to pick up where they left off on a project.
---

# 继续开发

从上次会话结束的地方接续开发。

## 第一步：找到最新的进度文档

按以下顺序查找进度文档：
1. `docs/progress-*.md` — 根据文件名中的日期找最新的一个
2. 项目根目录的 `PROGRESS.md` 或 `progress.md`
3. 项目根目录的 `TODO.md`、`ROADMAP.md` 或 `CHANGELOG.md`

读取找到的最新进度文档。

## 第二步：检查当前构建状态

运行项目的构建或类型检查命令，检测现有错误：
- TypeScript/Next.js：`npx tsc --noEmit 2>&1 | head -30` 或 `npm run build 2>&1 | tail -20`
- Vue：`npm run build 2>&1 | tail -20`
- 通用：检查 `package.json` 中是否有 `build`、`check` 或 `typecheck` 脚本

汇报发现的任何错误。

## 第三步：汇总并展示下一步

用用户偏好的语言（默认中文）简洁地汇报以下内容：
- **上次已完成**：上次会话完成了什么
- **进行中 / 卡住的**：已开始但未完成的内容，以及已知问题
- **下一步**：根据进度文档推荐的下一个任务

## 第四步：询问用户

询问要做哪个任务，或确认是否从推荐的下一步开始。

---

## 注意事项

- 如果没有进度文档，用 `git log --oneline -10` 查看最近提交历史作为备选
- 摘要保持简洁，最多 5–10 条要点
- 用户确认任务前不要开始实现任何内容
