# Skills

A collection of custom skills for [Claude Code](https://docs.anthropic.com/en/docs/claude-code) and compatible AI coding agents.

Each skill is a self-contained folder with a `SKILL.md` file that teaches the agent how to perform a specific task.

## Available Skills

| Skill | Description |
|-------|-------------|
| [humanize](./humanize/) | Review and rewrite text to remove AI-generated writing patterns |

## Installation

### Claude Code (Plugin Marketplace)

Register this repository as a plugin marketplace:

```
/plugin marketplace add tzengyuxio/skills
```

Then install a specific skill:

```
/plugin install humanize@tzengyuxio-skills
```

### Manual

Copy the desired skill folder into your Claude Code skills directory:

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
