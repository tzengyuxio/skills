---
name: hanjify
description: >
  Transform English text into Hanjified English — replacing words with CJK characters
  (Hanzi/Kanji/Hanja) while preserving English grammar structure. Uses okurigana-style
  morphology where Hanzi represents the word root and English suffixes remain as Roman letters.
  Produces three output versions: pure Hanjified, HTML Ruby annotation, and original text.
  Works on markdown files or inline text.
  Use this skill whenever the user mentions hanjify, hanjification, writing English in kanji
  or hanzi, mixing Chinese characters with English, creating an alternate writing system for
  English, or is curious about what English would look like written in CJK characters.
  Triggers on "/hanjify", "hanjify this", "convert to hanzi", "英語漢字化", "漢字化",
  "hanjify english", "english to hanzi", "write this in kanji", "英文漢字化".
argument-hint: [file-path]
allowed-tools: Read, Write, Edit, Glob
---

# Hanjify — 英語漢字化

Transform English text into Hanjified English — CJK characters carry meaning while English
grammar structure remains intact.

Hanjify is NOT translation. English word order, grammar, punctuation, and spacing are preserved
exactly. Only individual words are replaced with Hanzi equivalents. The result should read like
a plausible alternate-history writing system — as if English speakers independently adopted
Chinese characters at some point in history, producing a script that is neither English, Chinese,
nor Japanese, but something distinctive.

The character selection perspective: imagine an English native speaker who knows Hanzi and
looks up characters in a dictionary to transcribe English words. The chosen characters are
pan-CJK — mixing Chinese (traditional + simplified), Japanese kanji, Korean hanja, and
archaic characters. No bias toward any single tradition.

## Arguments

- `$0` — (Optional) Path to a markdown or text file containing English text. If omitted, ask
  for inline text or find the most recent English text in conversation context.

## Step 1: Load the Text

- If `$0` is provided, read the file.
- If no argument, find the most recent English text in the conversation, or ask the user.
- Validate that the input is predominantly English.

## Step 2: Hanjify the Text

Apply the rules below to convert English text into Hanjified form. Process the text word by word,
building an internal mapping table to ensure consistency throughout the document.

---

### Morphology Rules（形態規則）

The morphology follows a Japanese okurigana-inspired model: the Hanzi represents the word root,
and English inflectional/derivational suffixes remain as Roman letters attached directly to the
Hanzi (no space between Hanzi and suffix).

#### M1. Root + Suffix（漢字詞根＋英文後綴）[Hard]

The Hanzi represents the word stem. English suffixes attach directly after the Hanzi.

> **Before:** She moves the boxes carefully.
>
> **After:** 她 動s 其 箱es 慎ly.

#### M2. Regular Inflections（規則屈折變化）[Hard]

The following suffixes always remain as Roman letters attached to the Hanzi root:
`-s`, `-es`, `-ed`, `-ing`, `-er`, `-est`, `-ly`, `-ment`, `-ness`, `-ful`, `-less`,
`-able`, `-ible`, `-tion`, `-sion`, `-ous`, `-ive`, `-al`, `-fy`.

> **Before:** The beautiful gardens were carefully maintained by the strongest workers.
>
> **After:** 其 美ful 園s 是ed 慎ly 維持ed 以 其 強est 労ers.

#### M3. Irregular Past Forms（不規則過去式）[Hard]

Irregular past tense and past participle forms use the root Hanzi plus `-t` as a uniform marker.
This `-t` signals "this is an irregular inflected form" — it is a convention, not an English suffix.

> **Before:** I thought about what I saw and went home.
>
> **After:** 我 思t 関於 何 我 見t 與 行t 家.

Common examples: think→思/思t, go→行/行t, see→見/見t, eat→食/食t, come→来/来t,
give→与/与t, take→取/取t, write→書/書t, speak→言/言t, know→知/知t, stand→立/立t,
sit→座/座t, find→発見/発見t, buy→買/買t, run→走/走t, hold→持/持t, break→破/破t.

#### M4. Established CJK Compounds（既有複合詞）[Hard]

When an English word corresponds to a well-established CJK compound, use the compound directly.
These are treated as atomic units — do NOT split them into root + suffix.

> **Before:** Education gives us freedom and knowledge.
>
> **After:** 教育 与s 吾等 自由 與 知識.

Common compounds: education→教育, freedom→自由, government→政府, language→言語,
history→歴史, nature→自然, culture→文化, knowledge→知識, science→科学, economy→経済,
society→社会, music→音楽, religion→宗教, philosophy→哲学, university→大学,
technology→技術, information→情報, experience→経験, environment→環境, democracy→民主.

When a compound itself gets further suffixed, attach the suffix to the compound:
educational→教育al, governmental→政府al, knowledgeable→知識able.

#### M5. Comparative and Superlative（比較級與最高級）[Hard]

Use `-er` and `-est` suffixes attached to the Hanzi root. For periphrastic forms
(more/most + adjective), convert "more" to 更 and "most" to 最.

> **Before:** The taller man was the strongest but the most intelligent one won.
>
> **After:** 其 高er 男 是ed 其 強est 然 其 最 聰明 一 勝ed.

#### M6. Consistency Across Text（全文一致性）[Hard]

The same English root word MUST always map to the same Hanzi throughout the entire text.
Build and maintain an internal mapping table as you process. If the same root appears with
different suffixes (walk, walks, walked, walking), all forms must share the same Hanzi root.

> **Correct:** 彼 歩ed 至 其 門. 則 彼 歩ed 戻.
>
> **Wrong:** 彼 歩ed 至 其 門. 則 彼 行ed 戻. ← different Hanzi for same word "walked"

#### M7. Contractions（縮寫形式）[Hard]

Expand contractions before converting. The expanded form follows normal conversion rules.

> **Before:** I don't think he's going to the park. It's beautiful, isn't it?
>
> **After:** 我 行 不 思 彼 是 行ing 至 其 公園. 它 是 美ful, 是 不 它?

Common expansions: don't→do not, can't→cannot, won't→will not, I'm→I am,
it's→it is, he's→he is/he has, they're→they are, we'll→we will,
wouldn't→would not, shouldn't→should not, isn't→is not, aren't→are not.

#### M8. Phrasal Verbs（片語動詞）[Soft]

When a phrasal verb has a well-known CJK equivalent, convert as a unit. Otherwise, convert
each word individually.

> **Before:** She gave up the project but looked forward to the next one.
>
> **After:** 她 放棄ed 其 計画 然 期待ed 至 其 次 一.

Common phrasal verb compounds: give up→放棄, break down→崩壊, look for→探,
find out→発見, carry out→執行, turn off→消, set up→設立, pick up→拾,
make up→構成, point out→指摘, bring up→提起, come back→帰.

When no compound exists, convert each word: "run into"→走 入, "go along"→行 沿.

#### M9. Past Participle as Adjective（過去分詞作形容詞）[Hard]

When an irregular past participle is used as an adjective (not a verb), use the root Hanzi
plus `-n` to distinguish from the past tense `-t` marker.

> **Before:** A written letter lay on the broken table beside the forgotten book.
>
> **After:** 一 書n 信 横ed 於 其 破n 卓 旁 其 忘n 書.

This distinguishes: "He wrote a letter" (彼 書t 一 信) from "a written letter" (一 書n 信).
Regular past participles used as adjectives keep their `-ed`: "a closed door" (一 閉ed 門).

---

### Core Function Word Table（核心功能詞表）

These mappings are MANDATORY. Function words must ALWAYS use the specified Hanzi.
No variation is permitted.

**Intentional homography note:** Some different English words share the same Hanzi
(e.g., on/at→於, also/too→亦, between/during→間). This mirrors how real CJK writing
uses the same character for related concepts — context disambiguates, just as in
Chinese and Japanese. This is a feature, not a bug.

#### Articles

| English | Hanjified |
|---------|-----------|
| a, an | 一 |
| the | 其 |

#### Personal Pronouns

| English | Hanjified | English | Hanjified |
|---------|-----------|---------|-----------|
| I | 我 | we | 吾等 |
| you | 汝 | they | 彼等 |
| he | 彼 | me | 我 |
| she | 她 | him | 彼 |
| it | 它 | her (obj.) | 她 |
| | | us | 吾等 |
| | | them | 彼等 |

#### Possessive — use 之 as possessive marker

| English | Hanjified | English | Hanjified |
|---------|-----------|---------|-----------|
| my | 我之 | our | 吾等之 |
| your | 汝之 | their | 彼等之 |
| his | 彼之 | mine | 我之 |
| her (poss.) | 她之 | yours | 汝之 |
| its | 它之 | | |

#### Reflexive Pronouns — use 自 as reflexive marker

| English | Hanjified | English | Hanjified |
|---------|-----------|---------|-----------|
| myself | 我自 | ourselves | 吾等自 |
| yourself | 汝自 | yourselves | 汝等自 |
| himself | 彼自 | themselves | 彼等自 |
| herself | 她自 | itself | 它自 |

#### Interrogative and Relative

| English | Hanjified | English | Hanjified |
|---------|-----------|---------|-----------|
| who | 誰 | where | 何処 |
| whom | 誰 | when | 何時 |
| what | 何 | why | 何故 |
| which | 何 | how | 如何 |
| whose | 誰之 | | |

#### Demonstratives

| English | Hanjified | English | Hanjified |
|---------|-----------|---------|-----------|
| this | 此 | these | 此等 |
| that | 彼 | those | 彼等 |

#### Prepositions

| English | Hanjified | English | Hanjified |
|---------|-----------|---------|-----------|
| of | 之 | into | 入 |
| in | 在 | through | 經 |
| to | 至 | between | 間 |
| for | 為 | under | 下 |
| with | 與 | over | 上 |
| on | 於 | after | 後 |
| at | 於 | before | 前 |
| from | 自 | without | 無 |
| by | 以 | during | 間 |
| about | 関於 | against | 對 |
| around | 周 | among | 中 |

#### Conjunctions

| English | Hanjified | English | Hanjified |
|---------|-----------|---------|-----------|
| and | 與 | although | 雖 |
| or | 或 | so | 故 |
| but | 然 | than | 於 |
| because | 因 | as | 如 |
| if | 若 | unless | 除非 |
| when | 當 | whether | 是否 |
| while | 時 | | |

#### Auxiliary and Common Verbs

| English | Hanjified | English | Hanjified |
|---------|-----------|---------|-----------|
| is, am, are | 是 | will | 將 |
| was, were | 是ed | would | 將ed |
| been | 是t | should | 應 |
| being | 是ing | may | 可 |
| have, has | 有 | might | 可ed |
| had | 有ed | must | 須 |
| do, does | 行 | shall | 宜 |
| did | 行ed | | |
| can | 能 | | |
| could | 能ed | | |

#### Negation

| English | Hanjified | English | Hanjified |
|---------|-----------|---------|-----------|
| not | 不 | never | 從不 |
| no | 無 | none | 無一 |
| nor | 亦不 | neither | 亦不 |

#### Special Cases

**Infinitive "to" vs prepositional "to":**

| Context | English | Hanjified |
|---------|---------|-----------|
| Direction/destination | go **to** London | 行 **至** London |
| Infinitive marker | want **to** go | 欲 **to** 行 |

The infinitive "to" (before a verb) stays as English `to` — it is a grammatical particle
with no Hanzi equivalent, similar to how Japanese uses hiragana particles alongside kanji.

**Existential "there" vs locative "there":**

| Context | English | Hanjified |
|---------|---------|-----------|
| Location | I went **there** | 我 行t **彼処** |
| Existential | **There** is a book | **There** 是 一 書 |

Existential "there" (dummy subject in "there is/are") stays as English `there` — it has
no meaning to represent in Hanzi.

#### Common Adverbs and Determiners

| English | Hanjified | English | Hanjified |
|---------|-----------|---------|-----------|
| very | 甚 | here | 此処 |
| also | 亦 | there | 彼処 |
| too | 亦 | then | 則 |
| only | 僅 | now | 今 |
| just | 僅 | again | 再 |
| all | 皆 | soon | 即 |
| still | 仍 | yet | 尚 |
| already | 已 | perhaps | 或許 |
| always | 常 | together | 共 |
| often | 頻 | almost | 幾乎 |
| some | 某 | enough | 足 |
| many | 多 | quite | 頗 |
| much | 多 | | |
| every | 毎 | | |
| each | 各 | | |
| other | 他 | | |
| another | 他一 | | |
| same | 同 | | |
| such | 如此 | | |
| yes | 然 | | |

---

### Word Selection Checklist（詞語選擇清單）

#### W1. Concrete Nouns — Visually Descriptive Characters（具象名詞——象形優先）[Hard]

Prefer characters whose form or traditional meaning is visually or semantically transparent.
Choose the simplest, most universal character that directly depicts the concept.

> **Before:** The sun rose over the mountain and light filled the water.
>
> **After:** 其 日 昇ed 上 其 山 與 光 填ed 其 水.

Reference examples: sun→日, moon→月, water→水, mountain→山, tree→木, fire→火,
sky→天, star→星, river→川, wind→風, bird→鳥, fish→魚, horse→馬, dog→犬,
house→家, door→門, road→道, book→書, hand→手, eye→目, heart→心, person→人.

#### W2. Abstract Nouns — Compound Construction（抽象名詞——複合詞構造）[Hard]

Use established CJK compounds for abstract concepts. When no standard compound exists,
construct a two-character compound by combining meaning-bearing characters.

> **Before:** The beauty of nature lies in its complexity and mystery.
>
> **After:** 其 美 之 自然 存s 在 它之 複雑 與 神秘.

Reference examples: freedom→自由, education→教育, government→政府, language→言語,
history→歴史, culture→文化, knowledge→知識, power→力, truth→真, love→愛,
life→生命, death→死, time→時, peace→和平, war→戦, dream→夢, justice→正義.

#### W3. Verbs — Single Character Preferred（動詞——單字優先）[Hard]

Choose a single character that depicts the action. Suffixes attach to this character
per the morphology rules.

> **Before:** She walked slowly and looked at the birds singing in the trees.
>
> **After:** 她 歩ed 緩ly 與 見ed 於 其 鳥s 歌ing 在 其 木s.

Reference examples: eat→食, drink→飲, see→見, hear→聞, speak→言, walk→歩, run→走,
think→思, know→知, read→読, write→書, make→作, give→与, take→取, come→来, go→行,
stand→立, sit→座, sleep→眠, open→開, close→閉, love→愛, want→欲, need→要,
learn→学, teach→教, build→建, break→破, feel→感, buy→買, send→送, fly→飛, create→創.

#### W4. Adjectives — Hanzi Root + English Suffix（形容詞——漢字根＋英文後綴）[Hard]

Base adjective maps to a Hanzi. Comparative (-er), superlative (-est), and derivational
forms (-ful, -less, -ness, -ly) all attach as suffixes.

> **Before:** The beautiful sunset was more peaceful than the noisy morning.
>
> **After:** 其 美ful 日没 是ed 更 平和ful 於 其 喧ful 朝.

Reference examples: big→大, small→小, good→善, bad→悪, new→新, old→古, long→長,
short→短, high→高, low→低, strong→強, weak→弱, hot→熱, cold→冷,
bright→明, dark→暗, happy→楽, sad→悲, deep→深, heavy→重, young→若.

#### W5. Function Words — Strict Table Lookup（功能詞——嚴格查表）[Hard]

All function words (articles, pronouns, prepositions, conjunctions, auxiliaries, negation,
common adverbs) MUST use the exact mapping from the Core Function Word Table above.
No variation or creative substitution is allowed for these words.

#### W6. Proper Nouns — Keep Original English（專有名詞——保留英文）[Hard]

Names of people, places, brands, organizations, and other proper nouns stay in English.
Do NOT invent Hanzi substitutions for proper nouns.

> **Before:** John went to London to visit the British Museum.
>
> **After:** John 行t 至 London 至 訪ed 其 British Museum.

#### W7. Numbers — CJK Numerals（數字——漢字數字）[Hard]

Use CJK numeral characters for written-out numbers. Retain Arabic numerals for years,
specific dates, and large precise numbers when readability demands it.

> **Before:** Three hundred people gathered on October 15, 2024.
>
> **After:** 三百 人s 集ed 於 October 十五, 2024.

Reference: one→一, two→二, three→三, four→四, five→五, six→六, seven→七, eight→八,
nine→九, ten→十, hundred→百, thousand→千, million→百万, first→第一, second→第二,
third→第三, half→半, zero→零.

#### W8. Technical and Specialized Terms — Keep English（技術術語——保留英文）[Soft]

Terms with no natural Hanzi equivalent (algorithm, WiFi, DNA, HTTP, API, etc.) remain in
English. Well-established loanwords that have CJK equivalents may be converted
(computer→電脳, telephone→電話, television→電視).

> **Before:** The algorithm processes the DNA sequence using an API.
>
> **After:** 其 algorithm 処理s 其 DNA 配列 用ing 一 API.

#### W9. Character Tradition Neutrality（字源中立）[Soft]

When multiple valid Hanzi exist for the same concept, apply this preference order:
1. Characters common across Chinese, Japanese, and Korean traditions
2. Visually simpler characters (fewer strokes)
3. Characters whose meaning is most transparent to a pan-CJK reader

Do not systematically favor any single tradition (simplified Chinese, traditional Chinese,
Japanese shinjitai, etc.). The result should feel like a neutral, independent writing system.

> **Example:** For "school" — 学 (common, simple) preferred over 學 (traditional) or 斈 (archaic),
> unless the archaic form adds deliberate stylistic flavor.

#### W10. Compound Nouns（複合名詞）[Soft]

English compound nouns may be written as one word, hyphenated, or two words. When the
components map naturally to individual Hanzi, combine them into a Hanzi compound.
When a well-known CJK compound exists, prefer it.

> **Before:** The sunlight came through the bookshelf near the bedroom door.
>
> **After:** 其 日光 来t 經 其 書棚 近 其 寝室 門.

Examples: sunlight→日光, bookshelf→書棚, bedroom→寝室, newspaper→新聞,
airport→空港, earthquake→地震, rainbow→虹, homework→宿題, seawater→海水,
fireplace→暖炉, notebook→筆記帳.

When components don't naturally combine (e.g., "software", "deadline"), treat as a
single concept and find an appropriate CJK equivalent or keep in English per W8.

---

### Formatting Rules（格式規則）

#### F1. English Punctuation（英文標點）[Hard]

Keep periods, commas, question marks, exclamation marks, quotation marks, colons, semicolons,
and all other punctuation exactly as in English. Do NOT use Chinese punctuation
（。，？！「」：；）.

> **Correct:** "今日は," 她 言ed. "如何 是 汝?"
>
> **Wrong:** 「今日は，」她 言ed。「如何 是 汝？」

#### F2. English Word Spacing（英文詞距）[Hard]

Maintain spaces between words, exactly as in English. Do NOT collapse into Chinese-style
continuous text without spaces.

> **Correct:** 其 日 昇ed 上 其 山.
>
> **Wrong:** 其日昇ed上其山.

#### F3. Preserve Document Structure（保留文件結構）[Hard]

Preserve original paragraph breaks, line breaks, headings, lists, blockquotes, and all
other document structure from the source text.

#### F4. No Annotations in Hanjified Section（漢字化段落不含標注）[Hard]

The pure Hanjified output contains ONLY Hanzi + Roman suffixes. No English glosses,
parenthetical annotations, or ruby tags inline. Annotations belong exclusively in the
Ruby section.

---

## Step 3: Produce Three Output Versions

Output all three versions under clear headings. If a file path was provided, write to a new
file with `_hanjified` suffix.

### Format

```markdown
## Hanjified

[Pure hanjified text — Hanzi with Roman suffixes attached, no English originals.
Punctuation and spacing follow English conventions.]

## Ruby

[HTML ruby format. Every converted word gets a <ruby> tag.
The <rt> contains the original English word with its original casing and inflection.
Unconverted words (proper nouns, technical terms) appear without ruby tags.
Punctuation attaches to the preceding ruby element or word.]

## Original

[Original English text, completely unchanged.]
```

### Ruby Section Formatting

Each converted word uses this HTML pattern:

```html
<ruby>漢字suffix<rt>EnglishWord</rt></ruby>
```

Example for "The cat sat on the mat.":

```html
<ruby>其<rt>The</rt></ruby> <ruby>猫<rt>cat</rt></ruby> <ruby>座ed<rt>sat</rt></ruby> <ruby>於<rt>on</rt></ruby> <ruby>其<rt>the</rt></ruby> <ruby>蓆<rt>mat</rt></ruby>.
```

- One `<ruby>` element per word
- `<rt>` preserves the original English word's casing and inflection
- Unconverted words (proper nouns, technical terms) appear as plain text
- Punctuation follows the preceding element without a space before it

## Step 4: Consistency Audit

### Pass 1 — Consistency Check

Re-read the Hanjified output from start to finish. Verify that every occurrence of the same
English root word maps to the same Hanzi. If any inconsistency is found, standardize to the
first mapping used in the text.

Check function words especially — these must exactly match the Core Function Word Table.

### Pass 2 — Readability Check

Read the Hanjified text from the perspective of a reader familiar with CJK characters but not
with English. Can they guess the meaning of most content words? Flag any character choices that
are opaque or misleading, and replace with more semantically transparent alternatives.

## Step 5: Output

1. **File output:** Save to `_hanjified` suffix (e.g., `article.md` → `article_hanjified.md`).
   If user provides inline text (no file), output directly in the conversation.
2. **Sample comparison:** Show 3-5 representative sentences comparing all three versions
   (Original / Hanjified / Ruby) in a table or side-by-side format.
3. **Unconverted words:** List any words kept in English and briefly explain why
   (proper noun, technical term, no suitable Hanzi).
4. **Conversion rate:** Report the total word count and percentage converted
   (e.g., "287 of 312 words converted (92%)").

## Important Notes

- This is a **text transformation tool**, not a translator. English grammar is never altered.
- **Punctuation follows English conventions** (. , ? ! : ; "" '') — NOT Chinese punctuation.
- **Word spacing follows English** (spaces between words) — NOT Chinese continuous text.
- **Proper nouns stay in English** — never invent Hanzi for names of people, places, or brands.
- **Character selection is pan-CJK** — mix Chinese, Japanese, Korean, and archaic characters freely. Do not bias toward any single tradition.
- The result should look like a plausible "alternate history" writing system — distinctive and internally consistent.
- The **Core Function Word Table is mandatory** — these words must always use the specified mappings. Content words may be freely mapped following the example patterns and principles.
- **Do not reference external wordlist files.** All needed information is embedded in this skill.
- The okurigana-style morphology (Hanzi root + Roman suffixes) is the defining feature of this system. It solves the consistency problem: the same root always produces the same Hanzi, regardless of inflection.
