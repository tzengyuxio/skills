---
name: humanize
description: >
  Review and rewrite text to remove AI-generated writing patterns and adopt a more natural,
  human voice. Applies a checklist of known LLM writing tics (grandiose wording, tricolon abuse,
  vague attribution, hollow parallel structures, etc.) and rewrites flagged passages.
  Works on markdown files or inline text. Primarily targets Traditional Chinese writing
  but the principles apply to any language.
  Triggers on "/humanize", "make it sound human", "remove AI tone", "去 AI 味",
  "寫得更像人", "降低 AI 感".
argument-hint: [file-path]
allowed-tools: Read, Write, Edit, Glob
---

# Humanize — Remove AI Writing Patterns

Review text for common LLM writing characteristics and rewrite to sound more natural and human.

## Arguments

- `$0` — (Optional) Path to a markdown or text file. If omitted, the user should provide the text inline, or specify which file from the current conversation context to review.

## Step 1: Load the Text

- If `$0` is provided, read the file.
- If no argument, look for the most recently written or edited markdown file in the conversation context, or ask the user which text to review.

## Step 2: Scan for AI Writing Patterns

Read the checklist below and flag every instance found in the text. Categorize findings by severity:

- **Hard flags**: Patterns that almost certainly come from LLM output
- **Soft flags**: Patterns that humans sometimes use but LLMs overuse

### Checklist: Content Patterns

Reference: [Wikipedia:AI生成文的特徵](https://zh.wikipedia.org/wiki/Wikipedia:AI%E7%94%9F%E6%88%90%E6%96%87%E7%9A%84%E7%89%B9%E5%BE%B5)

#### C1. Grandiose Framing (用詞浮誇) [Hard]
Overstating importance, historical influence, or macro-level significance. Treating mundane facts as monumental.

Examples to flag:
- 「在...的歷史上扮演了舉足輕重的角色」
- 「堪稱...領域的里程碑」
- 「為...領域做出了不可磨滅的貢獻」
- 「這不僅是...更是...的重要轉折」
- 「深刻地改變了...的格局」
- Any sentence that says something is "transformative", "pivotal", "groundbreaking" without evidence

#### C2. Hollow Summary Sentences (空洞總結) [Hard]
Sentences that sound conclusive but convey zero specific information.

Examples to flag:
- 「總的來說，...」followed by repeating what was already said
- 「綜上所述，我們可以看到...」
- 「這些因素共同構成了...的獨特面貌」
- 「值得注意的是...」followed by something not especially noteworthy
- Opening with「毫無疑問」or「不可否認」

#### C3. Vague Attribution (模糊歸屬) [Hard]
Attributing opinions to unnamed authorities or inflating the breadth of agreement.

Examples to flag:
- 「許多專家認為」「學者普遍認為」without naming anyone
- 「廣泛被認為是」「被譽為」without saying by whom
- 「引發了廣泛的討論」without specifics
- 「受到了各界的關注」

#### C4. Superficial Analysis (表面分析) [Soft]
Inserting commentary that sounds analytical but says nothing substantive.

Examples to flag:
- 「這反映了...的深層趨勢」
- 「這一現象的背後，是...的結構性變化」
- 「這不僅體現了...也揭示了...」
- Any "analysis" that could apply to literally any topic with word substitution

#### C5. Promotional Tone (廣告宣傳語氣) [Soft]
Phrasing that reads like marketing copy rather than neutral description.

Examples to flag:
- 「獨特的」「創新的」「令人驚豔的」used without substantiation
- 「完美地融合了...與...」
- 「為讀者/用戶帶來全新的體驗」

### Checklist: Structure Patterns

#### S1. Tricolon / Triple Parallel Lists (三連排比) [Hard]
Three parallel items in a row, especially with escalating intensity. LLMs overuse this rhetorical device.

Examples to flag:
- 「...的深度、廣度與影響力」
- 「不僅...而且...更...」escalating triples
- 「從...到...再到...」
- Three consecutive bullet points each starting with bold keyword + colon + description

#### S2. Negative Parallel Structure (否定平行句) [Hard]
"This is not X, but Y" used to create false profundity.

Examples to flag:
- 「這不是...而是...」
- 「重點不在於...而在於...」
- 「與其說是...不如說是...」
- Especially when the distinction being drawn is trivial or obvious

#### S3. Formulaic Section Endings (公式化結尾) [Hard]
Every section ending with an uplifting or forward-looking statement.

Examples to flag:
- 「展望未來，...」
- 「隨著...的不斷發展，...將會...」
- 「我們有理由相信...」
- 「讓我們拭目以待」

#### S4. Mechanical Bullet Lists (機械式列表) [Soft]
Lists where every item follows the exact same "**Bold keyword** — explanation" template, especially when prose would be more natural.

#### S5. Excessive Markdown Emphasis (濫用粗體) [Soft]
Bolding keywords for emphasis throughout the text, as if writing a presentation slide rather than prose.

### Checklist: Vocabulary Patterns

#### V1. LLM Signature Words (AI 慣用詞) [Hard]
Words and phrases statistically overrepresented in LLM output:

**Chinese:**
- 「深入探討」「深入了解」
- 「至關重要」
- 「不可或缺」
- 「在當今...的時代」「在這個...的時代」
- 「發揮著...的作用」
- 「扮演著...的角色」
- 「一個...的旅程」(used metaphorically)
- 「賦能」「助力」
- 「打造」(overused for "create")
- 「驅動」(overused for "cause/lead to")
- 「核心」(overused as adjective)
- 「維度」(overused outside math/physics)
- 「生態系」「生態系統」(used metaphorically for non-biological systems)
- 「底層邏輯」
- 「方法論」(when「方法」suffices)
- 「範式」「範式轉移」
- 「賦予」(overused)

**English (for bilingual or English text):**
- "delve" / "delve into"
- "landscape" (metaphorical)
- "tapestry"
- "multifaceted"
- "in the realm of"
- "it's important/worth noting that"
- "This is not just X — it's Y"
- "at its core"
- "a testament to"

#### V2. Hedging Overuse (過度避險用語) [Soft]
Excessive qualifying language that weakens every statement:
- 「在某種程度上」「從某個角度來看」
- 「可以說是」
- 「相對而言」used repeatedly

### Checklist: Meta / Formatting

#### M1. Chatbot Artifacts (對話殘留) [Hard]
- 「希望這對你有幫助」
- 「你說得很對」「這是個好問題」
- 「讓我來為你...」
- 「以下是...」as a standalone intro sentence before a list
- Markdown code fences (```) in non-code documents

#### M2. Emoji in Prose [Hard]
Emoji used as bullet markers or inline decoration in non-casual writing.

#### M3. Numbered Paragraphs that Should Be Prose [Soft]
Content that reads as continuous prose but is artificially split into numbered sections.

## Step 3: Report Findings

Present findings to the user in a concise table:

```
| # | 位置 | 類型 | 原文片段 | 問題說明 |
|---|------|------|---------|---------|
| 1 | §引子 L3 | C1 浮誇 | 「扮演了舉足輕重的角色」 | 可直接說明具體做了什麼 |
| 2 | §結語 L2 | S2 否定平行 | 「這不是...而是...」 | 人為製造的對比，可簡化 |
```

At the end, provide a summary count: e.g., "共發現 12 處 AI 痕跡（Hard: 7, Soft: 5）"

## Step 4: Rewrite

Apply the following rewriting principles to fix all flagged passages:

### Rewriting Principles

1. **Specific over general** — Replace grand claims with concrete facts. "改變了格局" → describe what actually changed.

2. **Show, don't announce** — Remove meta-commentary about what you're about to say. Don't write "值得注意的是" — just say the noteworthy thing.

3. **Flat over escalating** — Replace tricolons with one precise word. "深度、廣度與影響力" → pick the one that actually matters.

4. **Earned conclusions only** — Remove summary sentences that don't add information beyond what the paragraphs already said.

5. **Name or drop** — If citing authorities, name them. If you can't name them, remove the attribution claim.

6. **Vary sentence structure** — Break out of the "Topic sentence → supporting detail → uplifting conclusion" template. Let some paragraphs end abruptly. Start some with details, not topic sentences.

7. **Allow imperfection** — Human writing has rough edges. Not every paragraph needs a tidy bow. Leave some threads hanging when appropriate.

8. **Use plain vocabulary** — Replace「深入探討」with「看看」「研究」「分析」. Replace「至關重要」with「很重要」or restructure to show importance through context.

9. **Keep bold for structure, not emphasis** — Bold only in headings and definition terms, not scattered throughout body text to highlight "key concepts."

10. **Prefer prose over lists** — If you can say it in two sentences, don't make it a three-item bullet list.

## Step 5: Output

1. **Default: do not overwrite the original file.** Save the rewritten version as a new file with a version suffix (e.g., `article-v2.md`). If the original already has a version number, increment it. However, if the user explicitly asks to overwrite or edit in place, do so directly.
2. Show a brief before/after comparison of the most significant changes (3-5 examples max).
3. State the total number of changes made.

## Important Notes

- This skill is a **reviewer and rewriter**, not a content generator. It works on existing text.
- Do NOT add new content, arguments, or information that wasn't in the original.
- Do NOT over-correct into stiff or academic prose. The goal is natural, not formal.
- Some flagged patterns may be intentional choices. When in doubt about a **Soft** flag, preserve the original.
- The checklist is not exhaustive. Use judgment to catch patterns that feel mechanical or formulaic even if they don't match a specific rule.
- When rewriting Chinese text, prefer 口語化 (conversational) over 書面語 (literary) register, unless the original deliberately uses formal register.
