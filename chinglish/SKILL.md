---
name: chinglish
description: >
  Transform Chinese text into Chinglish (中式英語) — English that is heavily influenced by
  Chinese grammar, word order, and thought patterns, producing the characteristic "中式英文"
  style found on signs, menus, instructions, and everyday speech. Can also take English text
  and re-render it through a Chinese-thinking lens to produce Chinglish.
  Applies a 25-item checklist covering article errors, copula dropping, topic-comment structure,
  verb confusion, literal calques, tense flattening, and more.
  Useful for humor, creative writing, language education, or demonstrating L1 transfer patterns.
  Triggers on "/chinglish", "寫成中式英文", "翻成中式英語", "Chinglish化", "translate to chinglish",
  "make it chinglish", "chinglish this", "中式英文".
argument-hint: [file-path]
allowed-tools: Read, Write, Edit, Glob
---

# Chinglish — 中式英語化

Transform text into Chinglish — English that sounds like it was produced by directly mapping
Chinese grammar, word order, and idiom onto English. The result should read like authentic
Chinglish: immediately recognizable as Chinese-influenced English, sometimes comical,
sometimes poetic, always structurally revealing of how Chinese and English differ.

Chinglish is NOT random bad English. It is **systematic** — each error reflects a real
interference pattern from Mandarin Chinese grammar. The output should feel like a native
Chinese speaker thinking in Chinese and rendering word-by-word into English.

## Arguments

- `$0` — (Optional) Path to a markdown or text file. If omitted, ask for inline text or
  find the most recent text in conversation context.

## Step 1: Load the Text

- If `$0` is provided, read the file.
- If no argument, find the most recent text in the conversation, or ask the user.
- The input can be **Chinese** (translate to Chinglish) or **English** (rewrite as Chinglish).

## Step 2: Apply Chinglish Patterns

Apply the rules below systematically to produce Chinglish output. When the input is Chinese,
first produce a rough literal translation, then apply the checklist. When the input is English,
restructure it through a Chinese-thinking lens.

The goal: every sentence should carry at least 2-3 Chinglish markers. Not every rule applies
to every sentence — use the ones that fit naturally.

---

### Grammar Patterns（語法模式）

#### G1. Drop or Misuse Articles [Hard, Light+]

Chinese has no articles (a, an, the). Chinglish either omits them entirely or inserts them
in wrong places. Omission is more common; hypercorrection (adding "the" everywhere) also occurs.

> **Standard:** I bought a book and a pen at the store.
>
> **Chinglish:** I bought book and pen at store.

> **Standard:** A friend of mine is a teacher. The school is very big.
>
> **Chinglish:** My one friend is teacher. School very big.

#### G2. Drop the Copula [Hard, Light+]

Chinese does not require "is/am/are" for adjective predicates (很好 = "very good", not
"is very good"). This produces sentences where the copula disappears.

> **Standard:** The weather is very good today.
>
> **Chinglish:** Today weather very good.

> **Standard:** This problem is too complicated.
>
> **Chinglish:** This problem too complicated.

#### G3. Topic-Comment Structure [Hard, Light+]

Chinese is topic-prominent: the topic comes first, then a comment about it. This differs
from English subject-verb-object. The topic may not be the grammatical subject at all.

> **Standard:** I've already eaten lunch.
>
> **Chinglish:** Lunch I already eat.

> **Standard:** My wallet was stolen.
>
> **Chinglish:** My wallet, stolen already.

> **Standard:** Speaking of this matter, I have no opinion.
>
> **Chinglish:** This matter, I no opinion.

#### G4. Flatten Tenses [Hard, Light+]

Chinese verbs do not conjugate for tense — time is conveyed by context and adverbs
(yesterday, already, will). Chinglish uses base-form verbs regardless of time reference.

> **Standard:** I went to Beijing last year and visited the Great Wall.
>
> **Chinglish:** I last year go Beijing, visit Great Wall.

> **Standard:** She has been working here for three years.
>
> **Chinglish:** She work here already three year.

> **Standard:** We will discuss this tomorrow.
>
> **Chinglish:** Tomorrow we discuss this.

#### G5. Subject-Verb Agreement Errors [Hard, Light+]

Chinese verbs have no singular/plural conjugation. The third-person "-s" is a frequent casualty.

> **Standard:** He speaks three languages.
>
> **Chinglish:** He speak three language.

> **Standard:** The machine works very well.
>
> **Chinglish:** This machine work very good.

#### G6. Drop or Misuse Plurals [Hard, Medium+]

Chinese nouns have no plural inflection — 一本書, 三本書 both use 書.
Chinglish either drops the plural "-s" or hypercorrects with double marking.

> **Standard:** There are many books on the table.
>
> **Chinglish:** Table on have many book.

> **Standard:** These three students are very smart.
>
> **Chinglish:** These three student very clever.

#### G7. Pronoun Gender Confusion [Soft, Medium+]

Chinese spoken language uses the same pronunciation "tā" for he/she/it (他/她/它 are
distinguished only in writing). Chinglish frequently swaps he/she.

> **Standard:** She told me her brother is coming. He will arrive tomorrow.
>
> **Chinglish:** She tell me she brother coming. She will arrive tomorrow.

#### G8. Double-Mark Conjunctions [Hard, Medium+]

Chinese uses paired conjunctions: 雖然...但是 (although...but), 因為...所以 (because...so).
English uses only one member of each pair. Chinglish keeps both.

> **Standard:** Although it was raining, we still went out.
>
> **Chinglish:** Although raining, but we still go out.

> **Standard:** Because the traffic was bad, I was late.
>
> **Chinglish:** Because traffic very bad, so I late.

---

### Vocabulary Patterns（詞彙模式）

#### V1. Open/Close for Everything [Hard, Medium+]

Chinese uses 開/關 (open/close) for many on/off operations. Chinglish extends "open" and
"close" far beyond their English range.

> **Standard:** Turn on the light. / Turn off the TV. / Start the car.
>
> **Chinglish:** Open the light. / Close the TV. / Open the car.

> **Standard:** Turn on the air conditioning.
>
> **Chinglish:** Open the air condition.

#### V2. "Give" as Universal Preposition [Soft, Medium+]

Chinese 給 serves as a preposition, benefactive marker, and passive marker.
Chinglish overuses "give" where English uses "for", "to", or other constructions.

> **Standard:** Let me introduce you to my friend.
>
> **Chinglish:** I give you introduce my friend.

> **Standard:** Please do me a favor.
>
> **Chinglish:** Please give me help.

#### V3. "Eat" + Everything [Soft, Medium+]

Chinese 吃 extends to medicine (吃藥), hardship (吃苦), surprise (吃驚), lawsuits (吃官司).
Chinglish calques these directly.

> **Standard:** Take some medicine. / I was surprised. / He suffered a lot.
>
> **Chinglish:** Eat some medicine. / I eat one surprise. / He eat many bitter.

#### V4. Adjective as Adverb [Hard, Medium+]

Chinese does not morphologically distinguish adjectives from adverbs. Chinglish uses the
adjective form where English requires "-ly" or an adverb.

> **Standard:** She sings beautifully.
>
> **Chinglish:** She sing very beautiful.

> **Standard:** Please drive carefully.
>
> **Chinglish:** Please careful drive.

#### V5. "Very" as Universal Intensifier [Hard, Medium+]

Chinese 很 (very) appears in nearly all positive adjective predicates, even without emphasis.
Chinglish uses "very" far more than natural English.

> **Standard:** I like this place. The food is good.
>
> **Chinglish:** I very like this place. Food very good.

> **Standard:** She's quite happy about it.
>
> **Chinglish:** She very happy.

#### V6. "Have" for Existence and Experience [Hard, Medium+]

Chinese 有 (have) serves as the existential "there is" and the experiential "have been".
Chinglish maps "have" onto both roles directly.

> **Standard:** There is a park nearby. / Have you ever been to Japan?
>
> **Chinglish:** Nearby have park. / You have go Japan before?

> **Standard:** There are many people here.
>
> **Chinglish:** Here have many people.

#### V7. "Play" as Universal Activity Verb [Soft, Medium+]

Chinese 玩 (play) covers a wide range of leisure activities.

> **Standard:** Use a computer. / Browse the internet. / Go sightseeing.
>
> **Chinglish:** Play computer. / Play internet. / Play around.

#### V8. Literal Idiom Calques [Hard, Medium+]

Translate Chinese four-character idioms (成語) and common expressions word-for-word
into English, preserving the Chinese imagery.

> **Standard (adding oil / 加油):** Come on! / You can do it!
>
> **Chinglish:** Add oil!

> **Standard (half-bucket water / 半桶水):** He only has a superficial understanding.
>
> **Chinglish:** He is half bucket water.

> **Standard (horse horse tiger tiger / 馬馬虎虎):** It's just so-so.
>
> **Chinglish:** Horse horse tiger tiger.

> **Standard (give you color see / 給你顏色看):** I'll teach you a lesson.
>
> **Chinglish:** Give you color see see.

> **Standard (people mountain people sea / 人山人海):** It's very crowded.
>
> **Chinglish:** People mountain people sea.

---

### Preposition and Word-Order Patterns（介詞與語序模式）

#### P1. Location/Time First [Hard, Medium+]

Chinese places time and location BEFORE the verb (在學校學習 = "at school study").
Chinglish follows this order rather than the English post-verb placement.

> **Standard:** I studied at the library yesterday afternoon.
>
> **Chinglish:** I yesterday afternoon at library study.

> **Standard:** We'll have a meeting in the conference room at 3 PM.
>
> **Chinglish:** We 3 o'clock at meeting room have meeting.

#### P2. Preposition Errors from Chinese Mapping [Hard, Medium+]

Chinese prepositions map differently to English ones. Common confusions:

- 在 → "at/in/on" used interchangeably
- 對 → "to" used where English needs other prepositions
- 跟 → "with/and" conflated

> **Standard:** I am interested in music. / She is good at math.
>
> **Chinglish:** I to music have interest. / She math very good.

> **Standard:** I discussed the plan with him.
>
> **Chinglish:** I with him discuss plan.

#### P3. Question Formation Without Inversion [Hard, Medium+]

Chinese questions use the same word order as statements, adding 嗎 or a question word in-situ.
Chinglish preserves this declarative word order.

> **Standard:** Where are you going? / Have you eaten yet?
>
> **Chinglish:** You go where? / You eat already?

> **Standard:** Can you help me? / What time does the store open?
>
> **Chinglish:** You can help me? / Store what time open?

---

### Structure Patterns（結構模式）

#### S1. Excessive Wordiness from Politeness Formulas [Soft, Heavy]

Chinese formal/polite register uses elaborate phrasing that produces stilted English
when translated literally.

> **Standard:** No entry — Emergency exit only.
>
> **Chinglish:** In order to ensure the safety of everyone, please do not enter
> this door during peacetime, this door is only used for emergency exit purpose.

> **Standard:** Do not touch.
>
> **Chinglish:** Please do not use hand to touch the exhibit.

#### S2. Sign and Menu Translation Style [Hard, Heavy]

Apply the characteristic Chinglish found on public signs, menus, and instructions:
overly literal, context-free, sometimes accidentally absurd. In **Heavy** mode, go all-in
with word-by-word dictionary substitution (e.g., picking the wrong polysemous entry).
In **Medium** mode, stick to straightforward literal translation without chasing absurd effects.

> **Standard:** Caution: Wet Floor
>
> **Chinglish (Heavy):** Carefully Slide
>
> **Chinglish (Medium):** Careful, Floor Slippery

> **Standard:** Stir-fried seasonal vegetables
>
> **Chinglish (Heavy):** Explode Fried Season Vegetable
>
> **Chinglish (Medium):** Stir Fry Time Vegetable

> **Standard:** Pull (on a door)
>
> **Chinglish (Heavy):** Drawing *(dictionary picked the wrong sense of 拉/pull)*
>
> **Chinglish (Medium):** Pull

#### S3. "Please" Overuse [Soft, Heavy]

Chinese polite requests frequently use 請 (please). Chinglish adds "please" to almost
every instruction, even where English would use a direct imperative.

> **Standard:** Insert your card. / Enter your password.
>
> **Chinglish:** Please insert your card. Please input your secret number.

> **Standard:** Take a number and wait.
>
> **Chinglish:** Please take number, please wait, please take seat.

#### S4. Comma Splice Chains [Hard, Medium+]

Chinese commonly chains multiple clauses with commas (逗號連綿) where English would use
separate sentences, conjunctions, or semicolons.

> **Standard:** He arrived at the office. He put down his bag. Then he made some coffee.
>
> **Chinglish:** He arrive office, put down bag, then make coffee.

> **Standard:** This city has a long history, beautiful scenery, and delicious food.
>
> **Chinglish:** This city history very long, scenery very beautiful, food very delicious.

---

## Step 3: Produce Chinglish Output

Apply the checklist to transform the entire text. Aim for consistent, recognizable Chinglish
throughout.

### Intensity Levels

Each rule is tagged with its minimum intensity (e.g., `[Hard, Light+]` = active from Light up;
`[Soft, Heavy]` = only in Heavy mode).

| Level | Active Rules | Effect |
|-------|-------------|--------|
| **Light** | G1-G5 (articles, copula, topic-comment, tenses, agreement) | Reads like a competent speaker with occasional L1 errors. |
| **Medium** (default) | Light + G6-G8, V1-V8, P1-P3, S4 | Clearly Chinglish — wrong word order, literal calques, comma chains. Mostly comprehensible. |
| **Heavy** | All rules including S1-S3 | Reads like a sign/menu machine translation — polite wordiness, dictionary mishaps, delightfully absurd. |

If the user doesn't specify, use **Medium**.

### Input-Specific Handling

**Chinese input → Chinglish:**
1. Work sentence-by-sentence. For each Chinese sentence, map Chinese words to English
   counterparts in **Chinese word order** — do NOT rearrange into English SVO order.
   This is the most important step: the Chinese sentence structure IS the Chinglish structure.
2. Keep Chinese time/place/manner adverb positions (before the verb).
3. Translate Chinese cultural concepts literally (加油→add oil, not "come on").
4. Then scan the result against the checklist and reinforce any patterns that are missing.

**English input → Chinglish:**
1. Mentally "back-translate" each sentence into Chinese to identify the natural Chinese structure.
2. Re-render in English following that Chinese structure: time → place → manner → verb.
3. Apply the checklist: drop articles, flatten tenses, replace vocabulary, etc.

### What Chinglish is NOT

Chinglish has a specific, predictable character. Avoid these traps:

- **NOT pidgin English** — Chinglish uses full English vocabulary, not a reduced pidgin lexicon.
  "Me no want" is pidgin; "I not want" is Chinglish.
- **NOT random grammar errors** — Every error must trace to a real Chinese grammar pattern.
  Random typos, malapropisms, or nonsense are not Chinglish.
- **NOT mockery or accent imitation** — Do not use "ching chong" sounds, fake phonetic
  spellings, or anything that mocks Chinese speakers. The goal is structural demonstration.

---

## Step 4: Output

1. **File output:** Save to `_chinglish` suffix (e.g., `article.md` → `article_chinglish.md`).
   If no file was provided, output directly in conversation.
2. **Show 3-5 representative sentence pairs** comparing Original and Chinglish versions.
3. **List applied patterns:** Note which major patterns (G/V/P/S) were most active.
4. (Optional, if user requests) **Chinglish density:** Report how many sentences carry 2+ markers.

---

## Important Notes

- This is a **stylistic transformation tool** for humor, education, and creative purposes.
- Chinglish is a **systematic** L1-transfer phenomenon, not random broken English. Every
  error should trace back to a real Chinese grammar pattern.
- Do NOT produce offensive, racist, or demeaning content. The goal is linguistic demonstration,
  not mockery. Chinglish is a natural interlanguage phenomenon worthy of study.
- When translating from Chinese, preserve the **Chinese thought pattern** — this is the core
  of what makes Chinglish feel authentic.
- The characteristic charm of Chinglish comes from its internal logic: it makes perfect sense
  if you know Chinese. Aim for that quality.
- Famous Chinglish examples like "People Mountain People Sea" and "Add Oil" have entered
  mainstream English awareness — embrace this tradition.
