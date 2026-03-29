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

References:
- [Wikipedia:AI生成文的特徵](https://zh.wikipedia.org/wiki/Wikipedia:AI%E7%94%9F%E6%88%90%E6%96%87%E7%9A%84%E7%89%B9%E5%BE%B5)
- [Wikipedia:Signs of AI writing](https://en.wikipedia.org/wiki/Wikipedia:Signs_of_AI_writing)

#### C1. Grandiose Framing (用詞浮誇) [Hard]
Overstating importance, historical influence, or macro-level significance. Treating mundane facts as monumental.

Words to watch: 「舉足輕重」「里程碑」「不可磨滅」「深刻地改變」「格局」; "transformative", "pivotal", "groundbreaking"

> **Before:** 加泰隆尼亞統計局於 1989 年正式成立，標誌著西班牙區域統計演變史上的關鍵時刻。這一舉措是西班牙全國範圍內更廣泛運動的一部分，旨在分散行政職能並加強區域治理。
>
> **After:** 加泰隆尼亞統計局成立於 1989 年，負責獨立於西班牙國家統計局收集和發布區域統計數據。

#### C2. Hollow Summary Sentences (空洞總結) [Hard]
Sentences that sound conclusive but convey zero specific information.

Words to watch: 「總的來說」「綜上所述」「值得注意的是」「毫無疑問」「不可否認」

> **Before:** 綜上所述，這些因素共同構成了台南獨特的文化面貌，使其成為台灣不可或缺的文化重鎮。
>
> **After:** (Delete the sentence — the preceding paragraphs already made the point with specifics.)

#### C3. Vague Attribution (模糊歸屬) [Hard]
Attributing opinions to unnamed authorities or inflating the breadth of agreement.

Words to watch: 「許多專家認為」「學者普遍認為」「廣泛被認為是」「被譽為」「受到各界關注」

> **Before:** 由於其獨特的特徵，浩來河引起了研究人員和保護主義者的興趣。專家認為它在區域生態系統中發揮著至關重要的作用。
>
> **After:** 根據中國科學院 2019 年的調查，浩來河有多種特有魚類。

#### C4. Superficial Analysis (表面分析) [Soft]
Inserting commentary that sounds analytical but says nothing substantive. Could apply to literally any topic with word substitution.

Words to watch: 「反映了...的深層趨勢」「這一現象的背後」「結構性變化」

> **Before:** 這不僅體現了在地社區對傳統文化的重視，也揭示了全球化浪潮下文化認同的深層變化。
>
> **After:** 社區每年投入約 200 萬元維護廟宇，居民參與率從十年前的 30% 上升到去年的 65%。

#### C5. Promotional Tone (廣告宣傳語氣) [Soft]
Phrasing that reads like marketing copy rather than neutral description.

Words to watch: 「獨特的」「創新的」「令人驚豔的」「完美融合」「全新體驗」「坐落於」「位於...的心臟地帶」「蓬勃發展」「豐富的文化底蘊」

> **Before:** 坐落在埃塞俄比亞貢德爾地區令人歎為觀止的區域內，這座充滿活力的城鎮擁有豐富的文化遺產和迷人的自然美景。
>
> **After:** Alamata Raya Kobo 是衣索比亞貢德爾地區的一座城鎮，以每週市集和一座 18 世紀教堂聞名。

#### C6. Detail Regression (細節消失) [Hard]
AI tends toward mean reversion — omitting specific, unusual, or granular details and replacing them with generic, positive descriptions. The result reads smoothly but loses the "sharp edges" that make writing informative.

Signs to flag:
- Specific numbers, dates, or measurements replaced with vague quantities ("many", "significant")
- Unusual or quirky details smoothed into generic descriptions
- Concrete examples replaced with abstract categories

Note: this pattern is about what's **missing** compared to the source material. When reviewing a rewrite, compare against the original to check for lost specifics.

> **Before (AI regression):** 許多居民參加了說明會，部分居民表達了擔憂。
>
> **After (details restored):** 37 位居民參加了說明會，其中 12 人反對，理由是噪音問題。

#### C7. Sycophantic Tone (諂媚語氣) [Hard]
Overly positive, people-pleasing language carried over from chatbot interaction patterns.

Words to watch: 「好問題」「您說得完全正確」「當然可以」「非常棒的觀點」; "Great question!", "Absolutely!", "You're right that..."

> **Before:** 好問題！您說得完全正確，這是一個複雜的話題。關於經濟因素，這是一個很好的觀點。
>
> **After:** 你提到的經濟因素確實相關。

### Checklist: Structure Patterns

#### S1. Tricolon / Triple Parallel Lists (三連排比) [Hard]
Three parallel items in a row, especially with escalating intensity. LLMs overuse this rhetorical device.

Words to watch: 「深度、廣度與影響力」「不僅...而且...更...」「從...到...再到...」

> **Before:** 活動包括主題演講、小組討論和社交機會。與會者可以期待創新、靈感和行業洞見。
>
> **After:** 活動有演講和小組討論，中間穿插自由交流的時間。

#### S2. Negative Parallel Structure (否定平行句) [Hard]
"This is not X, but Y" used to create false profundity. Comes in two variants:

**Variant A — Denial and redefinition** (「這不是 X，而是 Y」):
- 「這不是...而是...」「重點不在於...而在於...」「與其說是...不如說是...」

**Variant B — Escalation** (「不只是 X，更是 Y」):
- 「不只是...更是...」「這不僅僅是...它更代表了...」

> **Before:** 這不僅僅是節拍在人聲下流動；它是攻擊性和氛圍的一部分。這不僅僅是一首歌，更是一種宣言。
>
> **After:** 沉重的節拍強化了整體的攻擊性。

#### S3. Formulaic Section Endings (公式化結尾) [Hard]
Every section ending with an uplifting or forward-looking statement.

Words to watch: 「展望未來」「隨著...的不斷發展」「我們有理由相信」「讓我們拭目以待」

> **Before:** 展望未來，隨著技術的不斷發展，我們有理由相信台灣的半導體產業將會持續引領全球。
>
> **After:** (Delete — or replace with a specific fact about planned investment or capacity.)

#### S4. Mechanical Bullet Lists (機械式列表) [Soft]
Lists where every item follows the exact same "**Bold keyword** — explanation" template, especially when prose would be more natural.

> **Before:**
> - **用戶體驗：** 用戶體驗通過新介面得到顯著改善。
> - **性能：** 性能通過優化演算法得到增強。
> - **安全性：** 安全性通過端到端加密得到加強。
>
> **After:** 這次更新改善了介面、透過優化演算法加快了載入速度，並加入了端到端加密。

#### S5. Excessive Markdown Emphasis (濫用粗體) [Soft]
Bolding keywords for emphasis throughout the text, as if writing a presentation slide rather than prose.

> **Before:** 它融合了 **OKR（目標和關鍵結果）**、**KPI（關鍵績效指標）** 和 **商業模式畫布（BMC）**。
>
> **After:** 它融合了 OKR、KPI 和商業模式畫布等工具。

#### S6. Overuse of Em Dashes (濫用破折號) [Soft]
Excessive em dashes (——) for parenthetical insertions and dramatic pauses. One or two per article is fine; one per paragraph is a pattern.

> **Before:** 這個術語主要由荷蘭機構推廣——而不是由人民自己。你不會說「荷蘭，歐洲」作為地址——但這種錯誤標記仍在繼續——即使在官方文件中。
>
> **After:** 這個術語主要由荷蘭機構推廣，而不是由人民自己。你不會把「荷蘭，歐洲」當地址，但官方文件中這種錯誤標記仍在繼續。

#### S7. Formulaic "Despite" Conclusions (公式化「儘管」句型) [Hard]
The rigid formula: "Despite [positive aspects], [subject] faces challenges such as..." followed by vague optimism or speculation. Often appears in conclusion or "outlook" sections.

> **Before:** 儘管工業繁榮，Korattur 面臨著城市地區典型的挑戰，包括交通擁堵和水資源短缺。儘管存在這些挑戰，憑藉其戰略位置，Korattur 繼續蓬勃發展。
>
> **After:** 2015 年三座新 IT 園區啟用後，交通擁堵加劇。市政府於 2022 年啟動雨水排水工程，處理反覆發生的洪水問題。

#### S8. False Ranges (虛假範圍) [Soft]
"From X to Y" constructions where X and Y are not on a meaningful scale, used to create an illusion of breadth.

> **Before:** 我們穿越宇宙的旅程從大爆炸的奇點到宏偉的宇宙網，從恆星的誕生和死亡到暗物質的神秘舞蹈。
>
> **After:** 這本書涵蓋大爆炸、恆星形成和暗物質的現有理論。

### Checklist: Vocabulary Patterns

#### V1. LLM Signature Words (AI 慣用詞) [Hard]
Words and phrases statistically overrepresented in LLM output. A single instance may be coincidental; clusters are highly indicative.

Note: AI vocabulary shifts with model generations. This list covers commonly observed patterns but is not exhaustive. Some words below also appear in specific patterns (V3, V5) with more context on why they're problematic.

**Chinese:**
- 「深入探討」「深入了解」
- 「至關重要」
- 「不可或缺」
- 「在當今...的時代」「在這個...的時代」
- 「發揮著...的作用」「扮演著...的角色」
- 「一個...的旅程」(used metaphorically)
- 「賦能」「助力」
- 「打造」(overused for "create")
- 「驅動」(overused for "cause/lead to")
- 「核心」(overused as adjective)
- 「維度」(overused outside math/physics)
- 「生態系」「生態系統」(used metaphorically for non-biological systems)
- 「底層邏輯」「方法論」(when「方法」suffices)
- 「範式」「範式轉移」
- 「賦予」「蓬勃發展」「彰顯」「體現」
- 「致力於」「奠定基礎」
- 「深厚的...底蘊」「獨特魅力」

**English (for bilingual or English text):**
- "delve", "landscape" (metaphorical), "tapestry", "multifaceted"
- "in the realm of", "at its core", "a testament to"
- "it's important/worth noting that"
- "boasts", "bolstered", "garner", "meticulous(ly)"
- "intricate/intricacies", "interplay", "enduring"
- "fostering", "showcasing", "highlighting"
- "nestled", "vibrant", "diverse array", "in the heart of"
- "renowned", "commitment to"
- "rich" / "profound" (as generic intensifiers)

#### V2. Hedging Overuse (過度避險用語) [Soft]
Excessive qualifying language that weakens every statement.

Words to watch: 「在某種程度上」「從某個角度來看」「可以說是」「相對而言」

> **Before:** 可以潛在地可能被認為該政策可能會對結果產生一些影響。
>
> **After:** 該政策可能影響結果。

#### V3. Copula Avoidance (迴避繫詞) [Hard]
AI systematically avoids simple "is/are" (是/有) and substitutes with fancier verbs. This creates an unnaturally elevated register throughout the text.

**Chinese** — 「是」replaced with:「作為」「扮演」「代表」「象徵」「標誌著」

**English** — "is/are" replaced with: "serves as", "stands as", "represents", "marks", "features", "boasts"

> **Before:** Gallery 825 作為 LAAA 的當代藝術展覽空間。畫廊設有四個獨立空間，擁有超過 3000 平方英尺。
>
> **After:** Gallery 825 是 LAAA 的當代藝術展覽空間。畫廊有四個房間，共 3000 平方英尺。

#### V4. Elegant Variation (過度同義替換) [Hard]
Due to repetition penalty in LLM decoding, AI cycles through synonyms instead of naturally repeating a key term. Human writers repeat important words; AI makes the text read like a thesaurus exercise.

> **Before:** 主人公面臨許多挑戰。主要角色必須克服障礙。中心人物最終獲得勝利。英雄回到家中。
>
> **After:** 主人公面臨許多挑戰，但最終獲勝並回到家中。

#### V5. Present Participle Chains (分詞/動詞修飾連鎖) [Hard]
Attaching "-ing" participle phrases (or Chinese equivalents) to make vague analytical claims. Often co-occurs with C4 (Superficial Analysis) but is a distinct grammatical pattern.

**English:** "highlighting the importance of X, showcasing Y, and fostering Z"

**Chinese:** Chains of「了」-ending verb phrases used as pseudo-analysis.

> **Before:** 寺廟的藍色、綠色和金色色調與該地區的自然美景產生共鳴，象徵著德克薩斯州的藍帽花、墨西哥灣和多樣化的景觀，反映了社區與土地的深厚聯繫。
>
> **After:** 寺廟使用藍色、綠色和金色。建築師說這些顏色是為了呼應當地的藍帽花和墨西哥灣海岸。

#### V6. Filler Phrases (填充詞組) [Soft]
Wordy constructions that add no meaning. Replace with shorter equivalents.

Common substitutions:
- 「為了實現這一目標」→「為此」
- 「由於...的事實」→「因為」
- 「在這個時間點上」→「現在」
- 「具有...的能力」→「能」「可以」
- "In order to" → "To"
- "Due to the fact that" → "Because"
- "It is important to note that X" → "X"

### Checklist: Meta / Formatting

#### M1. Chatbot Artifacts (對話殘留) [Hard]
- 「希望這對你有幫助」
- 「讓我來為你...」
- 「以下是...」as a standalone intro sentence before a list
- Markdown code fences (```) in non-code documents

> **Before:** 以下是法國大革命的概述。希望這對您有幫助！如果您想讓我擴展任何部分，請告訴我。
>
> **After:** 法國大革命始於 1789 年，當時財政危機和糧食短缺引發了大規模動亂。

#### M2. Emoji in Prose [Hard]
Emoji used as bullet markers or inline decoration in non-casual writing.

> **Before:**
> 🚀 **啟動階段：** 產品在第三季發布
> 💡 **關鍵洞察：** 用戶更喜歡簡單
> ✅ **下一步：** 安排後續會議
>
> **After:** 產品在第三季發布。用戶研究顯示大家偏好簡潔。下一步是安排後續會議。

#### M3. Numbered Paragraphs that Should Be Prose [Soft]
Content that reads as continuous prose but is artificially split into numbered sections.

> **Before:**
> 1. 台南的廟宇文化歷史悠久。
> 2. 當地居民對宗教活動的參與度很高。
> 3. 每年舉辦的繞境活動吸引大量遊客。
>
> **After:** 台南的廟宇文化歷史悠久，當地居民對宗教活動的參與度很高。每年的繞境活動也吸引大量遊客。

#### M4. Markup Artifacts (標記語法殘留) [Hard]
Markup syntax leaking into rendered text, beyond just code fences.

Examples to flag:
- Markdown bold/italic syntax (`**text**`, `*text*`) appearing in non-Markdown output
- Markdown link syntax (`[text](url)`) in plain text or printed documents
- AI-internal reference tags: `oaicite`, `contentReference`, `turn0search0`
- Tracking parameters in URLs: `utm_source=chatgpt.com`, `utm_source=copilot.com`

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

11. **Repeat naturally** (counters V4) — Don't rotate synonyms to avoid repeating a word. If「公司」appears three times in a paragraph and that's natural, keep it. Human writers repeat key terms; thesaurus cycling is an AI tell.

12. **Use simple verbs** (counters V3) — Prefer「是」「有」「做了」over「作為」「扮演著」「代表了」. Prefer "is" over "serves as". Let the sentence be plain.

13. **Preserve sharp details** (counters C6) — Do not smooth out unusual facts, specific numbers, or rough edges into generic descriptions. If the original says "37 people attended", don't rewrite it as "many people attended".

### Personality and Voice

Removing AI patterns is only half the job. Sterile, voiceless writing is just as obvious as slop. After cleaning, consider whether the text needs voice:

**Vary rhythm.** Short sentences. Then longer ones that take their time. Mix it up. Three consecutive sentences of equal length feel algorithmic.

**Acknowledge complexity.** Real humans have mixed feelings. "This is impressive but also unsettling" beats "This is impressive."

**Allow first person when appropriate.** "I" is not unprofessional — it's honest. If the original text has a first-person voice, preserve and strengthen it.

**Trust the reader.** Don't explain metaphors. Don't soften every claim. State facts and let the reader react.

**Cut the bow.** Not every paragraph needs a neat closing. Some can just stop.

Note: this section applies mainly to essays, blog posts, and opinion pieces. For encyclopedic or technical writing, a neutral, impersonal voice is expected — focus on removing AI tics without injecting personality.

## Step 5: Anti-AI Audit

After completing the rewrite, perform a two-pass self-check:

**Pass 1 — Pattern scan:** Re-read the rewritten text against the same checklist from Step 2. The rewriting process itself commonly introduces new AI patterns. Fix any new flags.

**Pass 2 — Gut check:** Read the rewritten text as a whole and identify what still feels obviously AI-generated. List the remaining tells briefly (1-3 bullets). If any remain, revise those specific passages.

## Step 6: Output

1. **Default: do not overwrite the original file.** Save the rewritten version as a new file with a `_clean` suffix (e.g., `article.md` → `article_clean.md`). However, if the user explicitly asks to overwrite or edit in place, do so directly.
2. Show a brief before/after comparison of the most significant changes (3-5 examples max).
3. State the total number of changes made.

## Important Notes

- This skill is a **reviewer and rewriter**, not a content generator. It works on existing text.
- Do NOT add new content, arguments, or information that wasn't in the original.
- Do NOT over-correct into stiff or academic prose. The goal is natural, not formal.
- Some flagged patterns may be intentional choices. When in doubt about a **Soft** flag, preserve the original.
- The checklist is not exhaustive. Use judgment to catch patterns that feel mechanical or formulaic even if they don't match a specific rule.
- When rewriting Chinese text, prefer 口語化 (conversational) over 書面語 (literary) register, unless the original deliberately uses formal register.
