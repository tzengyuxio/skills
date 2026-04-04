# Skills

A collection of custom skills for [Claude Code](https://docs.anthropic.com/en/docs/claude-code) and compatible AI coding agents.

Each skill is a self-contained folder with a `SKILL.md` file that teaches the agent how to perform a specific task.

## Available Skills

| Skill | Description |
|-------|-------------|
| [humanize](./humanize/) | Review and rewrite text to remove AI-generated writing patterns |
| [dewesternise](./dewesternise/) | Review and rewrite Traditional Chinese text to remove Europeanized (歐化) writing patterns (25-item checklist) |
| [westernise](./westernise/) | Rewrite natural Traditional Chinese text to deliberately add 翻譯腔 (Europeanized translation accent) with 3 intensity levels (25-item checklist) |

## Installation

### Quick Install (single skill)

```bash
git clone --depth 1 https://github.com/tzengyuxio/skills.git /tmp/tz-skills && mkdir -p ~/.claude/skills && cp -r /tmp/tz-skills/humanize ~/.claude/skills/ && rm -rf /tmp/tz-skills
```

Replace `humanize` with any skill name from the table above.

### Plugin Marketplace

```
/plugin marketplace add tzengyuxio/skills
/plugin install humanize@tzengyuxio-skills
```

### Manual (if already cloned)

```bash
cp -r humanize ~/.claude/skills/humanize
```

## Creating a New Skill

Each skill folder contains at minimum a `SKILL.md` with YAML frontmatter:

```markdown
---
name: skill-name
description: What this skill does and when to trigger it
---

# Skill instructions here
```

See the [Agent Skills documentation](https://docs.anthropic.com/en/docs/claude-code/skills) for details.

## License

MIT
