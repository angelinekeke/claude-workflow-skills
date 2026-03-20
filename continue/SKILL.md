---
name: continue
description: Resume development from the last session by reading progress docs and summarizing what was done, what remains, and what to work on next. Use this skill when the user wants to pick up where they left off on a project.
---

# Continue Development

To resume a development session from where it was last left off:

## Step 1: Find the Latest Progress Document

Look for progress documents in the following locations, in order:
1. `docs/progress-*.md` — find the most recent file by date in the filename
2. `PROGRESS.md` or `progress.md` in the project root
3. `TODO.md`, `ROADMAP.md`, or `CHANGELOG.md` in the project root

Read the most recent progress document found.

## Step 2: Check Current Build Status

Run the project's build or type-check command to detect any existing errors:
- TypeScript/Next.js: `npx tsc --noEmit 2>&1 | head -30` or `npm run build 2>&1 | tail -20`
- Vue: `npm run build 2>&1 | tail -20`
- General: check `package.json` for a `build`, `check`, or `typecheck` script

Report any errors found.

## Step 3: Summarize and Present Next Steps

Present a concise summary in the user's preferred language covering:
- **Completed last session**: what was finished
- **In progress / blocked**: anything started but not done, and any known issues
- **Up next**: the recommended next task(s) based on the progress doc

## Step 4: Ask the User

Ask which task to work on, or confirm they want to start with the recommended next step.

---

## Tips

- If no progress document exists, check `git log --oneline -10` for recent commit history as a fallback
- Keep the summary short — 5–10 bullet points max
- Do not start implementing anything until the user confirms the task
