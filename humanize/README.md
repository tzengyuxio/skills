# Humanize

Remove AI-generated writing patterns and rewrite text to sound more natural and human.

## What It Does

This skill scans text for common LLM writing characteristics — grandiose framing, hollow summaries, vague attributions, tricolon abuse, AI signature vocabulary, and more — then rewrites flagged passages into plain, natural prose.

Primarily targets Traditional Chinese (繁體中文) writing, but the checklist and principles apply to any language.

## Usage

```
/humanize path/to/article.md
```

Or invoke it without arguments after writing or editing a markdown file in the conversation.

**Trigger phrases:** `/humanize`, "make it sound human", "remove AI tone", "去 AI 味", "寫得更像人", "降低 AI 感"

## How It Works

1. **Scan** — Checks text against a detailed checklist of AI writing patterns, categorized as Hard flags (almost certainly AI) and Soft flags (overused by AI but sometimes human)
2. **Report** — Presents findings in a table with location, pattern type, and explanation
3. **Rewrite** — Applies rewriting principles (specific over general, show don't announce, plain vocabulary, etc.) to fix all flagged passages
4. **Output** — Saves rewritten version as a new file (e.g., `article-v2.md`), preserving the original

## Pattern Categories

| Category | ID | Examples |
|----------|----|---------|
| Content | C1–C6 | Grandiose framing, hollow summaries, vague attribution, superficial analysis, promotional tone, detail regression |
| Structure | S1–S7 | Tricolon abuse, negative parallelisms, formulaic endings, mechanical lists, excessive bold, em dash overuse, formulaic "despite" pattern |
| Vocabulary | V1–V5 | LLM signature words, hedging overuse, copula avoidance, elegant variation (synonym cycling), participle chains |
| Meta | M1–M4 | Chatbot artifacts, emoji in prose, numbered paragraphs as prose, markup artifacts |

## Rewriting Principles

- Specific over general
- Show, don't announce
- Flat over escalating
- Earned conclusions only
- Name or drop (attributions)
- Vary sentence structure
- Allow imperfection
- Use plain vocabulary
- Bold for structure, not emphasis
- Prefer prose over lists
- Repeat naturally (don't cycle synonyms)
- Use simple verbs (「是」over「作為」)
- Preserve sharp details (don't smooth out specifics)

## Installation

Copy the skill folder into your Claude Code skills directory:

```bash
cp -r humanize ~/.claude/skills/humanize
```

Or, if this repository is registered as a plugin marketplace:

```
/plugin marketplace add tzengyuxio/skills
/plugin install humanize@tzengyuxio-skills
```

## Changelog

### v2 — 2026-03-29

- Added 7 new patterns: C6 (detail regression), S6 (em dash overuse), S7 (formulaic "despite"), V3 (copula avoidance), V4 (elegant variation), V5 (participle chains), M4 (markup artifacts)
- Expanded V1 signature word lists (Chinese and English)
- Split S2 into two variants: denial-redefinition vs escalation
- Added 3 rewriting principles: repeat naturally, use simple verbs, preserve sharp details
- Added self-check step: rewritten text is scanned against the same checklist before output
- Added English Wikipedia reference

### v1 — 2026-03-29

- Initial release with 16 patterns (C1–C5, S1–S5, V1–V2, M1–M3) and 10 rewriting principles

## References

- [Wikipedia:AI生成文的特徵](https://zh.wikipedia.org/wiki/Wikipedia:AI%E7%94%9F%E6%88%90%E6%96%87%E7%9A%84%E7%89%B9%E5%BE%B5)
- [Wikipedia:Signs of AI writing](https://en.wikipedia.org/wiki/Wikipedia:Signs_of_AI_writing)
