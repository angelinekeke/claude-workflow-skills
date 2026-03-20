# claude-dev-skills

A collection of Claude Code custom skills for developers who work on multi-phase projects across multiple sessions.

---

## Skills Included

### `/continue` — Resume from Last Session
Reads your latest progress document, checks build status, and presents a summary of what was done and what's next — so you can pick up exactly where you left off without re-explaining context.

### `/progress` — Save Session Progress
Writes a structured progress document (`docs/progress-YYYY-MM-DD.md`) summarizing what was completed, what remains, known issues, and next steps. Run this before ending a session so your future self (and Claude) can resume smoothly.

---

## Installation

### Option A: Personal (works across all your projects)

```bash
# Clone into your global Claude skills directory
git clone https://github.com/YOUR_USERNAME/claude-dev-skills ~/.claude/skills/
```

Or copy individual skill folders:

```bash
cp -r continue ~/.claude/skills/
cp -r progress ~/.claude/skills/
```

### Option B: Project-specific (only for one repo)

```bash
# From your project root
git clone https://github.com/YOUR_USERNAME/claude-dev-skills .claude/skills-temp
cp -r .claude/skills-temp/continue .claude/skills/
cp -r .claude/skills-temp/progress .claude/skills/
rm -rf .claude/skills-temp
```

Or simply copy the skill folders you want into `.claude/skills/` in your project.

---

## Usage

Once installed, type the slash command in Claude Code:

| Command | What it does |
|---------|-------------|
| `/continue` | Read latest progress doc → check build → show summary → ask what to work on |
| `/progress` | Summarize this session → write `docs/progress-YYYY-MM-DD.md` |

**Recommended workflow:**
1. Start every session with `/continue`
2. End every session with `/progress`

---

## Directory Structure

```
claude-dev-skills/
├── README.md
├── continue/
│   └── SKILL.md        # /continue skill
└── progress/
    └── SKILL.md        # /progress skill
```

---

## Why These Skills?

If you work on long-running projects across many Claude Code sessions, you've probably experienced:
- Re-explaining what you were doing at the start of every session
- Losing track of where you stopped mid-feature
- Forgetting to document progress before closing

These two skills turn "document-driven development" into a one-command habit.

---

## Contributing

PRs welcome. If you have a skill that helps with multi-session project development, feel free to submit it.

---

## License

MIT
