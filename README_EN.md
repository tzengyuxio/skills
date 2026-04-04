# Skills

A collection of custom skills for [Claude Code](https://docs.anthropic.com/en/docs/claude-code) and compatible AI coding agents.

Each skill is a self-contained folder with a `SKILL.md` file that teaches the agent how to perform a specific text transformation task.

> [中文版](./README.md)

## Available Skills

### AI Writing Style

| Skill | Function |
|-------|----------|
| [humanize](./humanize/) | Remove AI-generated writing patterns (26-item checklist, supports English & Chinese) |

### Translation Accent Tools

Style transformation tools for Europeanized Chinese (翻譯腔), each with a 25-item checklist. These two skills are inverse operations.

| Skill | Function |
|-------|----------|
| [dewesternise](./dewesternise/) | Remove Europeanized writing patterns from Chinese text |
| [westernise](./westernise/) | Deliberately add translation accent (3 intensity levels) |

### Classical Chinese Rewriting

Rewrite modern Chinese into different historical literary styles, each with a 20-22 item checklist.

| Skill | Style | Representative Works |
|-------|-------|---------------------|
| [wenyan-xianqin](./wenyan-xianqin/) | Pre-Qin Philosophical (先秦諸子體) | Analects, Zhuangzi, Han Feizi |
| [wenyan-hanwei](./wenyan-hanwei/) | Han-Wei Historical Narrative (漢魏史傳體) | Shiji, Hanshu, Records of the Three Kingdoms |
| [wenyan-guwen](./wenyan-guwen/) | Tang-Song Classical Essay (唐宋古文體) | Han Yu, Su Shi, Ouyang Xiu |
| [wenyan-huaben](./wenyan-huaben/) | Vernacular Fiction (話本小說體) | Water Margin, Romance of the Three Kingdoms, Dream of the Red Chamber |

## Installation

### Ask Your AI to Install

Paste the following prompt to your AI assistant (Claude Code, Cursor, Windsurf, etc.):

```
Install the humanize skill from https://github.com/tzengyuxio/skills into my
global skills directory (~/.claude/skills/). Use git clone --depth 1, copy only
the needed skill folder, and clean up the temp files.
```

Replace `humanize` with any skill name. To install into the current project, change the path to `.claude/skills/`.

### One-Liner

```bash
git clone --depth 1 https://github.com/tzengyuxio/skills.git /tmp/tz-skills \
  && mkdir -p ~/.claude/skills \
  && cp -r /tmp/tz-skills/humanize ~/.claude/skills/ \
  && rm -rf /tmp/tz-skills
```

Replace `humanize` with any skill name, or list multiple (e.g. `dewesternise westernise`). To install into a project, change `~/.claude/skills` to `.claude/skills`.

### Plugin Marketplace

```
/plugin marketplace add tzengyuxio/skills
/plugin install humanize@tzengyuxio-skills
```

## License

MIT
