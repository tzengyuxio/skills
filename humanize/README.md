# Humanize

Remove AI-generated writing patterns and rewrite text to sound more natural and human.

## What It Does

This skill scans text for common LLM writing characteristics — grandiose framing, hollow summaries, vague attributions, tricolon abuse, AI signature vocabulary, and more — then rewrites flagged passages into plain, natural prose.

Primarily targets Traditional Chinese (繁體中文) writing, but the checklist and principles apply to any language.

## Installation

One-liner (clone and install):

```bash
git clone --depth 1 https://github.com/tzengyuxio/skills.git /tmp/tz-skills && mkdir -p ~/.claude/skills && cp -r /tmp/tz-skills/humanize ~/.claude/skills/ && rm -rf /tmp/tz-skills
```

Or via plugin marketplace in Claude Code:

```
/plugin marketplace add tzengyuxio/skills
/plugin install humanize@tzengyuxio-skills
```

Manual (if already cloned):

```bash
cp -r humanize ~/.claude/skills/humanize
```

## Usage

```
/humanize path/to/article.md
```

Or invoke it without arguments after writing or editing a markdown file in the conversation.

**Trigger phrases:** `/humanize`, "make it sound human", "remove AI tone", "去 AI 味", "寫得更像人", "降低 AI 感"

## How It Works

1. **Scan** — Checks text against a detailed checklist of 26 AI writing patterns, categorized as Hard flags (almost certainly AI) and Soft flags (overused by AI but sometimes human)
2. **Report** — Presents findings in a table with location, pattern type, and explanation
3. **Rewrite** — Applies 13 rewriting principles and personality/voice guidance to fix flagged passages
4. **Audit** — Two-pass anti-AI self-check: pattern re-scan + "what still feels AI?" gut check
5. **Output** — Saves rewritten version as a new file with `_clean` suffix (e.g., `article_clean.md`), preserving the original

## Pattern Categories

| Category | ID | Patterns |
|----------|----|----------|
| Content | C1–C7 | Grandiose framing, hollow summaries, vague attribution, superficial analysis, promotional tone, detail regression, sycophantic tone |
| Structure | S1–S8 | Tricolon abuse, negative parallelisms, formulaic endings, mechanical lists, excessive bold, em dash overuse, formulaic "despite", false ranges |
| Vocabulary | V1–V6 | LLM signature words, hedging overuse, copula avoidance, elegant variation, participle chains, filler phrases |
| Meta | M1–M4 | Chatbot artifacts, emoji in prose, numbered paragraphs as prose, markup artifacts |

Each pattern includes a Before/After example demonstrating the expected rewrite.

## Rewriting Principles

1. Specific over general
2. Show, don't announce
3. Flat over escalating
4. Earned conclusions only
5. Name or drop (attributions)
6. Vary sentence structure
7. Allow imperfection
8. Use plain vocabulary
9. Bold for structure, not emphasis
10. Prefer prose over lists
11. Repeat naturally (don't cycle synonyms)
12. Use simple verbs (「是」over「作為」)
13. Preserve sharp details (don't smooth out specifics)

Plus a **Personality and Voice** section for essays and opinion pieces: vary rhythm, acknowledge complexity, allow first person, trust the reader, cut the bow.

## Changelog

### v3 — 2026-03-29

- Added Before/After examples for every pattern
- Added "Personality and Voice" section for injecting human voice after cleanup
- Upgraded self-check to two-pass anti-AI audit (pattern re-scan + gut check)
- Added 3 new patterns: C7 (sycophantic tone), S8 (false ranges), V6 (filler phrases)
- Total: 26 patterns, 13 rewriting principles

### v2 — 2026-03-29

- Added 7 new patterns: C6 (detail regression), S6 (em dash overuse), S7 (formulaic "despite"), V3 (copula avoidance), V4 (elegant variation), V5 (participle chains), M4 (markup artifacts)
- Expanded V1 signature word lists (Chinese and English)
- Split S2 into two variants: denial-redefinition vs escalation
- Added 3 rewriting principles: repeat naturally, use simple verbs, preserve sharp details
- Added self-check step
- Added English Wikipedia reference

### v1 — 2026-03-29

- Initial release with 16 patterns (C1–C5, S1–S5, V1–V2, M1–M3) and 10 rewriting principles

## References

- [Wikipedia:AI生成文的特徵](https://zh.wikipedia.org/wiki/Wikipedia:AI%E7%94%9F%E6%88%90%E6%96%87%E7%9A%84%E7%89%B9%E5%BE%B5)
- [Wikipedia:Signs of AI writing](https://en.wikipedia.org/wiki/Wikipedia:Signs_of_AI_writing)
- [blader/humanizer](https://github.com/blader/humanizer) — English-focused humanizer skill, inspiration for personality/voice section and before/after examples
- [op7418/Humanizer-zh](https://github.com/op7418/Humanizer-zh) — Simplified Chinese adaptation of blader/humanizer
