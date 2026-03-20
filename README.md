# claude-dev-workflow-skills

适用于 Claude Code 的自定义 Skill 合集，专为跨会话、多阶段项目开发者设计。

---

## 包含的 Skills

### `/continue` — 从上次进度继续开发
自动读取最新的进度文档，检查构建状态，汇总上次做了什么、还剩什么——让你每次开新会话都能无缝接上，不用重新交代背景。

### `/progress` — 保存本次会话进度
在会话结束时写一份结构化的进度文档（`docs/progress-YYYY-MM-DD.md`），记录已完成、未完成、已知问题和下一步计划。下次开始时配合 `/continue` 使用，形成完整的开发工作流闭环。

### `/daily-log` — 生成每日工作记录
一天结束时，生成完整的工作记录文档，包含：今天完成的所有事项、踩过的坑与解决方案、经验总结与改进思考、后续待办。比 `/progress` 更全面，适合做个人成长记录或团队复盘。

---

## 安装方法

### 方式 A：全局安装（所有项目都能用）

```bash
git clone https://github.com/angelinekeke/claude-dev-workflow-skills ~/.claude/skills/claude-dev-workflow-skills
cp -r ~/.claude/skills/claude-dev-workflow-skills/continue ~/.claude/skills/
cp -r ~/.claude/skills/claude-dev-workflow-skills/progress ~/.claude/skills/
cp -r ~/.claude/skills/claude-dev-workflow-skills/daily-log ~/.claude/skills/
```

### 方式 B：项目内安装（仅限单个项目）

在你的项目根目录执行：

```bash
mkdir -p .claude/skills
git clone https://github.com/angelinekeke/claude-dev-workflow-skills /tmp/claude-dev-workflow-skills
cp -r /tmp/claude-dev-workflow-skills/continue .claude/skills/
cp -r /tmp/claude-dev-workflow-skills/progress .claude/skills/
cp -r /tmp/claude-dev-workflow-skills/daily-log .claude/skills/
```

---

## 使用方式

安装后，在 Claude Code 中直接输入斜杠命令即可：

| 命令 | 效果 |
|------|------|
| `/continue` | 读取最新进度文档 → 检查构建状态 → 展示摘要 → 询问下一步任务 |
| `/progress` | 汇总本次会话 → 写入 `docs/progress-YYYY-MM-DD.md` |
| `/daily-log` | 记录全天工作 → 踩坑解决方案 → 经验总结 → 写入每日工作记录文档 |

**推荐工作流：**
1. 每次开始会话时运行 `/continue`
2. 每次结束会话前运行 `/progress`
3. 每天结束时运行 `/daily-log`，记录全天踩坑与收获

---

## 目录结构

```
claude-dev-workflow-skills/
├── README.md
├── LICENSE
├── continue/
│   └── SKILL.md        # /continue 技能定义
├── progress/
│   └── SKILL.md        # /progress 技能定义
└── daily-log/
    └── SKILL.md        # /daily-log 技能定义
```

---

## 为什么需要这两个 Skills？

如果你在用 Claude Code 做长周期项目，大概遇到过这些情况：
- 每次开新会话都要重新解释项目背景和当前进度
- 功能做到一半，下次不知道从哪接
- 会话结束前忘记记录进度，下次白费时间回忆

这两个 Skill 把「文档驱动开发」变成一个两条命令的习惯。

---

## 贡献

欢迎 PR。如果你有适合多会话项目开发的 Skill，欢迎提交。

---

## License

MIT
