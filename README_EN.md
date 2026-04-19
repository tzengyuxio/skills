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

### Chinese-English Language Mashup

English varieties and writing system transformations — convert text into Chinese-influenced English styles or hybrid scripts.

| Skill | Function |
|-------|----------|
| [chinglish](./chinglish/) | Transform Chinese or English into Chinglish — systematic L1-transfer patterns from Chinese grammar |
| [singlish](./singlish/) | Transform any text into Singlish — Singaporean English creole blending Hokkien, Malay, Cantonese, and Tamil |
| [hanjify](./hanjify/) | Transform English into Hanjified English — Hanzi carries meaning, English grammar stays intact (okurigana-style morphology) |

### Regional Chinese Varieties

Transform text into regional sociolects / written registers of contemporary Chinese-speaking communities, each with a checklist and three intensity levels.

| Skill | Function | Example |
|-------|----------|---------|
| [taiwan-mandarin](./taiwan-mandarin/) | Transform text into Taiwan Mandarin — Hokkien/Japanese loanwords, phonological respellings (偶/粉/素/降), BBS-era 注音文, and sentence-final particles (啦/喔/齁/耶) | [demo](./taiwan-mandarin/examples/demo.md) |
| [hongkong-chinese](./hongkong-chinese/) | Transform text into Hong Kong Chinese — HK-specific terms (巴士/的士/雪櫃), transliterations (荷里活/梳化/三文治), English code-mixing, AB/BA word-order flips; Heavy mode extends to full written Cantonese (係/唔/嘅/咗/佢/呢/嗰) | [demo](./hongkong-chinese/examples/demo.md) |

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
