---
name: progress
description: Write a progress document summarizing what was completed, what remains, known issues, and next steps for the current session. Use this skill at the end of a work session or when the user asks to save progress.
---

# Write Progress Document

To save a progress summary for the current session:

## Step 1: Gather What Changed This Session

Collect changes made during this session using available context:
- Check `git diff HEAD` or `git status` if the project is a git repo
- Review the conversation history for files written, edited, or discussed
- Note any features implemented, bugs fixed, or decisions made

## Step 2: Identify Remaining Work

Based on the original task and what was completed, identify:
- Tasks started but not finished
- Tasks not yet started that were planned
- Any blockers or unresolved issues discovered

## Step 3: Write the Progress Document

Write a Markdown file to `docs/progress-YYYY-MM-DD.md` (use today's date).

The document must include these sections:

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

Write the document in the user's preferred language (default: Chinese 中文).

## Step 4: Confirm

Report the file path where the progress document was saved, and briefly list the "next steps" so the user can see them at a glance before closing the session.

---

## Tips

- If `docs/` directory does not exist, create it
- Keep each bullet point concise — one line per item
- The "下一步" (next steps) section is the most important: make it actionable and specific so the next session can start immediately
- If there are unresolved errors or blockers, document them clearly in "已知问题"
