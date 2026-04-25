---
name: hanjify
description: >
  Transform English text into Hanjified English — replacing words with CJK characters
  (Hanzi/Kanji/Hanja) while preserving English grammar structure. Uses a hybrid morphology
  where inflectional suffixes stay as Roman letters and derivational suffixes/prefixes
  become Hanzi. Produces three output versions: pure Hanjified, HTML Ruby annotation,
  and original text. Works on markdown files or inline text.
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

> **Canonical spec**: `docs/spec.md` in [tzengyuxio/hanjify](https://github.com/tzengyuxio/hanjify)
> ([live tool](https://hanjify.tzengyuxio.me)). This skill implements the same spec via LLM,
> with context-aware disambiguation that the table-lookup web tool cannot perform.

Hanjify is NOT translation. English word order, grammar, punctuation, and spacing are preserved
exactly. Only individual words are replaced with Hanzi equivalents. The result reads like a
plausible alternate-history writing system — as if English speakers independently adopted
Chinese characters at some point in history, producing a script that is neither English, Chinese,
nor Japanese, but something distinctive.

The character selection perspective: imagine an English native speaker who knows Hanzi and
looks up characters in a dictionary to transcribe English words. The chosen characters are
pan-CJK — mixing Chinese (traditional + simplified), Japanese kanji, Korean hanja, and
archaic characters. No single-tradition bias.

## Arguments

- `$0` — (Optional) Path to a markdown or text file containing English text. If omitted, ask
  for inline text or find the most recent English text in conversation context.

## Step 1: Load the Text

- If `$0` is provided, read the file.
- If no argument, find the most recent English text in the conversation, or ask the user.
- Validate that the input is predominantly English.

## Step 2: Hanjify the Text

Apply the rules below. Process the text word by word, building an internal mapping table to
ensure consistency. As an LLM implementation, you can disambiguate polysemous words by context
where a lookup table cannot.

---

### Morphology Rules (M1–M9)

**Hybrid strategy**: inflectional changes keep Roman letters; derivational changes become Hanzi.

#### M1. Root + Suffix [Hard]

The Hanzi represents the word stem. Suffixes attach directly after the Hanzi (no space).

> **Before:** She moves the boxes carefully.
>
> **After:** 伊 動s the 箱es 慎重地.

#### M2. Suffix and Prefix Strategy [Hard]

**Priority order**: full-word lookup (wordlist) → suffix/prefix rules → original passthrough.

##### M2a. Inflections — keep Roman letters

| Inflection | Use | Example |
|---|---|---|
| `-s` / `-es` | Plural | move→動 / moves→動s |
| `-ed` | Regular past | walk→歩 / walked→歩ed |
| `-ing` | Progressive / gerund | run→走 / running→走ing |
| `-er` | Comparative | big→大 / bigger→大er |
| `-est` | Superlative | big→大 / biggest→大est |

Irregular past forms use `-t` (see M3).

##### M2b. Derivational suffixes — convert to Hanzi

| Suffix | Hanzi | Example |
|---|---|---|
| `-er` / `-or` / `-ar` | 者 | teacher→教者, actor→演者 |
| `-ist` | 家 | novelist→小說家 |
| `-ician` | 師 | musician→音楽師 |
| `-eer` | 師 | engineer→工程師 |
| `-man` | 人 | horseman→馬人 |
| `-ee` | 受 | employee→雇受 |
| `-ess` | 者 (not gendered; specific overrides via wordlist, e.g., princess→王女) |
| `-ly` | 地 | actually→實際地 |
| `-ful` / `-al` / `-ous` / `-ive` | 的 | beautiful→美的 |
| `-able` / `-ible` | 的 | readable→読的 |
| `-less` | 无…的 | useless→无使用的, harmless→无害的 |
| `-fy` / `-ize` / `-ise` | 化 | industrialize→工業化 |
| `-tion` / `-sion` / `-ment` / `-ness` / `-ance` / `-ancy` | (use idiomatic CJK compound) | creation→創造, movement→運動 |
| `-thing` | 物 | something→某物, nothing→无物 |
| `-body` | 体 | somebody→某体, anybody→任体 |
| `-where` | 処 | anywhere→任何処 |
| `-one` | 一 | someone→某一 |

##### M2c. Derivational prefixes — convert to Hanzi

| Prefix | Hanzi | Example |
|---|---|---|
| `un-` | 不 | unhappy→不喜, unknown→不知 |
| `non-` | 非 | non-smoker→非煙者 |
| `re-` | 再 | rebuild→再建, restart→再起 |
| `any-` | 任 | anybody→任体 |
| `some-` | 某 | something→某物 |
| `every-` | 毎 | everyone→毎一 |
| `no-` | 无 | nobody→无体, nothing→无物 |

##### M2d. Idiomatic CJK compounds win over rules

If the English word maps to an idiomatic CJK compound (princess→王女, review→審查,
return→帰, meeting→会議), use that compound directly even if the rule would suggest
something else.

#### M3. Irregular Past Forms [Hard]

Irregular past tense and past participle use root Hanzi + `-t` as a uniform marker.

> **Before:** I thought about what I saw and went home.
>
> **After:** 予 思t 関於 何 予 見t 与 行t 家.

Common forms (full list in §Reference):
think→思 / 思t, go→行 / 行t, see→見 / 見t, eat→食 / 食t, come→来 / 来t,
give→与 / 与t, take→取 / 取t, write→書 / 書t, speak→言 / 言t, know→知 / 知t,
stand→立 / 立t, sit→座 / 座t, find→発見 / 発見t, buy→買 / 買t, run→走 / 走t,
hold→持 / 持t, break→破 / 破t, make→作 / 作t.

#### M4. Established CJK Compounds [Hard]

When an English word corresponds to a well-established CJK compound, use the compound directly.

> **Before:** Education gives us freedom and knowledge.
>
> **After:** 教育 与s 吾等 自由 与 知識.

Common compounds: education→教育, freedom→自由, government→政府, language→言語,
history→歴史, nature→自然, culture→文化, knowledge→知識, science→科斈, economy→経済,
society→社会, music→音楽, religion→宗教, philosophy→哲斈, university→大斈,
technology→技術, information→情報, experience→経験, environment→環境, democracy→民主.

#### M5. Comparative and Superlative [Hard]

Use `-er` / `-est` (M2a). Periphrastic forms: more→更, most→最.

> **Before:** The taller man was the strongest but the most intelligent one won.
>
> **After:** the 高er 男 是ed the 強est 但 the 最 聰明 一 勝ed.

#### M6. Consistency Across Text [Hard]

Same English root word maps to the same Hanzi throughout the document. Build and maintain
an internal mapping table.

#### M7. Contractions [Hard]

Expand contractions before converting:
don't→do not, can't→cannot, won't→will not, isn't→is not, wouldn't→would not,
I'm→I am, it's→it is, he's→he is, they're→they are, we'll→we will, etc.

> **Before:** I don't think he's going to the park.
>
> **After:** 予 行 不 思 彼 是 行ing to the 公園.

#### M8. Phrasal Forms [Soft]

Phrasal verbs (idiomatic):
give up→放棄, break down→崩壊, look for→探, find out→発見, carry out→執行,
turn off→消, set up→設立, pick up→拾, make up→構成, point out→指摘,
bring up→提起, come back→帰.

Conjunctive `as X as` phrases (literal compose):
as well as → 如善如, as long as → 如長如, as soon as → 如即如,
as much as → 如多如, as many as → 如多如, as far as → 如远如,
as if → 如若, as though → 如雖.

#### M9. Past Participle as Adjective [Hard]

Past participles used as adjectives keep the same form as the verb (sole `-t` marker;
no separate `-n` marker).

> **Before:** A written letter lay on the broken table.
>
> **After:** 一 書t 信 横ed 於 the 破t 卓.

---

### Core Function Word Table

These mappings are mandatory. No variation.

**Intentional homography note**: some pairs share Hanzi by design — context disambiguates:
on/at→於, between/during→間, and/with→与, many/much→多, but/yes→然.

#### Articles (preserved as English — see §Don't-Convert List)

| English | Hanjified |
|---|---|
| a, an, the | (kept as English) |

#### Personal Pronouns

| English | Hanjified | English | Hanjified |
|---|---|---|---|
| I | 予 | we | 吾等 |
| you | 尔 | they | 彼等 |
| he | 彼 | me | 予 |
| she | 伊 | him | 彼 |
| it | 它 | her (obj) | 伊 |
| | | us | 吾等 |
| | | them | 彼等 |

#### Possessive — `之` as marker

| English | Hanjified | English | Hanjified |
|---|---|---|---|
| my / mine | 予之 | our | 吾等之 |
| your / yours | 尔之 | their | 彼等之 |
| his | 彼之 | | |
| her (poss) | 伊之 | | |
| its | 它之 | | |

#### Reflexive — `自` as marker

| English | Hanjified | English | Hanjified |
|---|---|---|---|
| myself | 予自 | ourselves | 吾等自 |
| yourself | 尔自 | yourselves | 尔等自 |
| himself | 彼自 | themselves | 彼等自 |
| herself | 伊自 | itself | 它自 |

#### Interrogative & Relative

| English | Hanjified | English | Hanjified |
|---|---|---|---|
| who / whom | 誰 | where | 何処 |
| whose | 誰之 | when (interrog.) | 何時 |
| what | 何 | when (conj.) | 当 |
| which (interrog.) | 何 | why | 何故 |
| which (relative) | 其中 | how | 如何 |

For `when` / `which`: use the interrogative form (何時 / 何) when the word is at the start
of a `?`-terminated clause; otherwise use the connective/relative form (当 / 其中). As an
LLM, you can also disambiguate by syntactic context (subject-aux inversion etc.).

#### Demonstratives

| English | Hanjified | English | Hanjified |
|---|---|---|---|
| this | 這 | these | 這等 |
| that | 那 | those | 那等 |

#### Prepositions

| English | Hanjified | English | Hanjified |
|---|---|---|---|
| of | (kept) | through | 経 |
| in | (kept) | between | 間 |
| to | (kept) | under | 下於 |
| for | 為 | over | 上於 |
| with | 与 | after | 後 |
| on | (kept) | before | 前 |
| at | (kept) | without | 不与 |
| from | 从 | during | 間 |
| by | 以 | against | 反対 |
| about | 関於 | among | 其中 |
| around | 周辺 | | |
| into | 入 | | |

Note: `under → 下於` and `over → 上於` to distinguish from up→上 / down→下 (intentional avoidance).

#### Conjunctions

| English | Hanjified | English | Hanjified |
|---|---|---|---|
| and | 与 | although | 雖然 |
| or | 或 | so | 故 |
| but | 但 | than | 於 |
| because | 因為 | as | 如 |
| if | 若 | unless | 除非 |
| when | 当 | whether | 是否 |
| while | 正当 | | |

#### Auxiliary and Common Verbs

| English | Hanjified | English | Hanjified |
|---|---|---|---|
| is, am, are | 是 | will | 将 |
| was, were | 是ed | would | 将ed |
| been | 是t | should | 応 |
| being | 是ing | may | 可 |
| have, has | 有 | might | 可ed |
| had | 有ed | must | 須 |
| do, does | 行 | shall | 宜 |
| did | 行ed | | |
| can | 能 | | |
| could | 能ed | | |

#### Negation

| English | Hanjified | English | Hanjified |
|---|---|---|---|
| not | 不 | never | 从不 |
| no | 无 | none | 无一 |
| nor | 亦不 | neither | 亦不 |

#### Common Adverbs and Determiners

| English | Hanjified | English | Hanjified |
|---|---|---|---|
| very | 甚 | here | 此処 |
| also | 亦 | there (loc.) | 彼処 |
| too | 亦 | there (existential) | (kept as English) |
| only | 唯一 | then | 則 |
| just | 僅 | now | 今 |
| all | 全 | again | 再 |
| still | 仍 | soon | 不久 |
| already | 既 | yet | 卻 |
| always | 始終 | perhaps | 或許 |
| often | 常常 | together | 共集 |
| some | 某 | almost | 幾乎 |
| many | 多 | enough | 足夠 |
| much | 多 | quite | 頗為 |
| every | 每 | yes | 是 |
| each | 各 | such | 如此 |
| other | 其他 | | |
| another | 另 | | |
| same | 相樣 | | |

---

### Don't-Convert List

Preserve these as **English** (do not convert to Hanzi):

1. **Articles**: `a`, `an`, `the`
2. **Short virtual prepositions**: `of`, `in`, `to`, `on`, `at`
3. **Infinitive `to`**: when before a verb (`want **to** go`)
4. **Existential `there`**: in `There is/are...` constructs
5. **Western proper nouns**: people, places, brands (Einstein, Newton, Paris, London, etc.)
6. **Untranslatable technical terms**: DNA, HTTP, API, WiFi (terms with no natural CJK form)
7. **Relative `which`**: rendered as `其中` in spec but if context makes the relative role clear,
   you can keep `which` as English for readability (LLM judgement)

#### Special: CJK-cultural-sphere proper nouns

Names and places from China / Japan / Korea / Vietnam (incl. HK / Macau / Taiwan) **are** converted
back to their Hanzi form: 中国, 日本, 韓国, 越南, 台湾, 香港, 澳門, 東京, 首爾, 北京, 京都,
富士山, 長江, 黃海, 孔子, 老子, 孫逸仙, 秀吉.

---

### Word Selection Checklist (W1–W10)

#### W1. Concrete Nouns — Visually Descriptive [Hard]

Prefer characters whose form or traditional meaning is transparent.

> sun→日, moon→月, water→水, mountain→山, tree→木, fire→火, sky→天, star→星,
> river→川, wind→風, bird→鳥, fish→魚, horse→馬, dog→犬, house→家, door→門,
> road→道, book→書, hand→手, eye→目, heart→心, person→人.

#### W2. Abstract Nouns — Compound Construction [Hard]

Use established CJK compounds; otherwise combine two semantic characters.

> freedom→自由, knowledge→知識, power→力, truth→真, love→愛, life→生命,
> death→死, time→時, peace→和平, war→戦, dream→夢, justice→正義.

#### W3. Verbs — Single Character [Hard]

Single character + suffix per M2.

> eat→食, drink→飲, see→見, hear→聞, speak→言, walk→歩, run→走, think→思,
> know→知, read→読, write→書, make→作, give→与, take→取, come→来, go→行,
> stand→立, sit→座, sleep→眠, open→開, close→閉, love→愛, want→欲, need→要.

#### W4. Adjectives — Hanzi Root + Suffix [Hard]

Base adjective maps to Hanzi; comparative/derivational forms via M2a/M2b.

> big→大, small→小, good→善, bad→悪, new→新, old→古, long→長, short→短,
> high→高, low→低, strong→強, weak→弱, hot→熱, cold→冷, bright→明, dark→暗,
> happy→楽, sad→悲, deep→深, heavy→重, young→若.

#### W5. Function Words — Strict Table [Hard]

Use the Core Function Word Table above. No variation.

#### W6. Proper Nouns — Keep English (with CJK-cultural-sphere exception) [Hard]

> John 行t 至 London. （Western — kept English）
>
> 孔子 言t 重要 之 言. （CJK — converted）

#### W7. Numbers — CJK Numerals [Hard]

Written-out numbers → Hanzi. Years/dates → Arabic numerals.

> Three hundred people gathered on October 15, 2024.
>
> → 三百 人s 集ed 於 October 十五, 2024.

#### W8. Technical Terms [Soft]

- Untranslatable acronyms (DNA, HTTP, API, WiFi) → kept English
- Terms with idiomatic CJK forms → use them: algorithm→演祘法, computer→電脳, telephone→電話

#### W9. Character Tradition Neutrality [Soft]

Priority: (1) characters common across CN/JP/KR; (2) simpler form (existing structure
preferred over stroke-count reduction); (3) most transparent meaning.

#### W10. Compound Nouns [Soft]

> sunlight→日光, bookshelf→書棚, bedroom→寝室, newspaper→新聞, airport→空港,
> earthquake→地震, rainbow→虹, homework→宿題, seawater→海水, fireplace→暖炉.

---

### Conflict Avoidance Rule

If a function word's single-character Hanzi would conflict with another high-frequency word
of **different role**, switch to a two-character form:

| Function word | Conflicts with | Switched to |
|---|---|---|
| under | down | **下於** |
| over | up | **上於** |
| enough | foot | **足夠** |
| yet | 高尚 / 時尚 etc. | **卻** |

The intentional-homography exceptions (on/at→於, between/during→間, and/with→与, many/much→多,
but/yes→然) are NOT conflicts — they share role/category.

---

### Formatting Rules (F1–F4)

#### F1. English Punctuation [Hard]

Keep `.` `,` `?` `!` `:` `;` `"` `'` etc. exactly as in English. Do **NOT** use Chinese
punctuation `。，？！「」：；`.

> ✓ "今日, " 伊 言ed. "如何 是 尔?"
>
> ✗ 「今日，」伊 言ed。「如何 是 尔？」

#### F2. English Word Spacing [Hard]

Maintain spaces between words. Do **NOT** use Chinese-style continuous text.

> ✓ the 日 昇ed 上 the 山.
>
> ✗ the日昇ed上the山.

#### F3. Preserve Document Structure [Hard]

Preserve paragraphs, line breaks, headings, lists, blockquotes — all structure stays.

#### F4. No Annotations Inline [Hard]

Pure Hanjified output contains only Hanzi + Roman suffixes. No English glosses, parenthetical
annotations, or ruby tags inline. Annotations belong only in the Ruby section.

---

### Character Form Adoption (字形採用)

The base is **Traditional Chinese**, with these explicit substitutions:

**Common (CN-simp + JP shinjitai same form)**: 来, 国, 数, 体, 宝, 将, 与, 党, 医, 参, 断, 属

**CN-simp adopted**: 从, 当, 无, 时, 单, 战, 选, 举, 达, 园, 远, 电, 务, 离, 亲, 虽, 杀, 灵, 压, 尽, 众, 尘

**JP shinjitai adopted**: 机, 楽, 鉄, 経, 関, 対, 応, 効, 温, 脳, 拡, 発, 観, 齢, 焼, 児, 奨, 浅, 銭

**Old / variant chars adopted**: 学→斈, 覺→斍, 算→祘, 氣→气, 世→卋, 獸→嘼, 雞→鷄, 收→収

**Kept Traditional (no simplification)**: 黑, 動, 傳, 隊, 鄰, 勝, 華, 畢, 風, 圍, 織, 識, 圖, 線, 筆

---

## Step 3: Produce Three Output Versions

Output all three under clear headings. If a file path was provided, write to a new file
with `_hanjified` suffix.

```markdown
## Hanjified

[Pure hanjified text — Hanzi with Roman inflections, derivational suffixes/prefixes
already converted to Hanzi. Punctuation and spacing follow English conventions.]

## Ruby

[HTML ruby format. Every converted word gets a <ruby> tag.
The <rt> contains the original English word with its casing and inflection.
Unconverted words (proper nouns, technical terms, items in the Don't-Convert List)
appear without ruby tags. Punctuation attaches to the preceding element.]

## Original

[Original English text, completely unchanged.]
```

### Ruby Section Formatting

```html
<ruby>漢字suffix<rt>EnglishWord</rt></ruby>
```

Example for "The cat sat on the mat.":

```html
The <ruby>猫<rt>cat</rt></ruby> <ruby>座t<rt>sat</rt></ruby> on the <ruby>蓆<rt>mat</rt></ruby>.
```

- One `<ruby>` element per converted word
- `<rt>` preserves the original English word's casing and inflection
- Items in the Don't-Convert List (`The`, `on`, `the` here) appear as plain text
- Irregular past forms wrap the `-t` marker into the same `<ruby>`: `<ruby>行t<rt>went</rt></ruby>`

## Step 4: Consistency Audit

### Pass 1 — Consistency Check

Re-read the Hanjified output. Verify every occurrence of the same English root word maps to
the same Hanzi. If inconsistencies exist, standardize to the first mapping used.

Function words must exactly match the Core Function Word Table.

### Pass 2 — Readability Check

Read the Hanjified text from the perspective of a CJK-character-literate reader who doesn't
know English. Can they guess most content words? Replace opaque or misleading characters with
more transparent alternatives.

### Pass 3 — Conflict Audit

Check for unhandled conflicts (single-char function word colliding with content word). If
detected, switch to two-character form per the Conflict Avoidance Rule.

## Step 5: Output

1. **File output**: Save with `_hanjified` suffix (e.g., `article.md` → `article_hanjified.md`).
   For inline text, output directly in the conversation.
2. **Sample comparison**: Show 3–5 representative sentences in a table (Original / Hanjified / Ruby).
3. **Unconverted words**: List any items kept in English with reason (proper noun, technical
   term, in Don't-Convert List, no suitable Hanzi).
4. **Conversion rate**: Total word count and percentage converted (e.g., "287 of 312 words
   converted (92%)").

## Important Notes

- This is a **text transformation**, not a translation. English grammar is never altered.
- **Punctuation follows English** (`. , ? ! : ; "" ''`) — NEVER Chinese punctuation.
- **Word spacing follows English** (spaces between words) — NEVER Chinese continuous text.
- **Western proper nouns stay English**; CJK-cultural-sphere proper nouns convert to Hanzi.
- **Character selection is pan-CJK** but biased toward universal forms (CJK-three common chars
  preferred over single-tradition variants).
- The result should look like a plausible "alternate-history" writing system — distinctive,
  internally consistent, readable to anyone familiar with both English and Hanzi.
- The **Core Function Word Table is mandatory** — these words must always use specified mappings.
- **Idiomatic CJK compounds win** over mechanical rules (princess → 王女, not 主者).
- The hybrid morphology (inflections in Roman, derivations in Hanzi) is the spec's defining
  feature. It solves the consistency problem: same root always produces the same Hanzi
  regardless of inflection, and reduces visual clutter compared to all-Roman-suffix.
