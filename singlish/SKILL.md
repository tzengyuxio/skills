---
name: singlish
description: >
  Transform text into Singlish (Colloquial Singaporean English) — an English-based creole
  shaped by Hokkien, Malay, Cantonese, Mandarin, and Tamil. Features discourse particles
  (lah, lor, meh, hor, leh), topic-comment structure, zero copula, optional tense/plural
  marking, "got" for existence, "kena" passive, verb reduplication, and multilingual loanwords.
  Applies a 27-item checklist covering grammar, discourse particles, vocabulary, and structure.
  Useful for creative writing, cultural appreciation, language education, or humor.
  Triggers on "/singlish", "寫成新加坡英語", "translate to singlish", "make it singlish",
  "singlish this", "新加坡式英文", "write in singlish".
argument-hint: [file-path]
allowed-tools: Read, Write, Edit, Glob
---

# Singlish — 新加坡式英語

Transform text into Singlish — Colloquial Singaporean English, a creole language born from
the contact of English, Hokkien, Malay, Cantonese, Mandarin, Teochew, and Tamil. The result
should sound like an authentic Singaporean speaking casually at a kopitiam or hawker centre.

Singlish is NOT broken English. It is a **fully-formed creole** with its own fixed grammar,
phonology, and pragmatic system. Every feature reflects systematic substrate influence from
Southeast Asian languages. The output should feel natural and internally consistent — like
a native Singlish speaker, not a foreigner imitating one badly.

## Arguments

- `$0` — (Optional) Path to a markdown or text file. If omitted, ask for inline text or
  find the most recent text in conversation context.

## Step 1: Load the Text

- If `$0` is provided, read the file.
- If no argument, find the most recent text in the conversation, or ask the user.
- The input can be **English** (rewrite as Singlish), **Chinese** (translate to Singlish),
  or **any language** (translate to Singlish).

## Step 2: Apply Singlish Patterns

Apply the rules below systematically. The goal: every sentence should carry at least 2-3
Singlish markers. Not every rule applies to every sentence — use the ones that fit naturally.

Singlish exists on a creole continuum. This skill targets the **mesolectal to basilectal**
range — clearly colloquial, distinctly Singaporean, but still comprehensible.

---

### Grammar Patterns（語法模式）

#### G1. Topic-Comment Structure [Hard, Light+]

Singlish is topic-prominent like Chinese and Malay. Place the topic (known information) first,
then comment on it. The topic need not be the grammatical subject.

> **Standard:** The weather in this country is very hot.
>
> **Singlish:** Dis country weather very hot one.

> **Standard:** You can't trust that person.
>
> **Singlish:** Dat joker there cannot trust.

> **Standard:** You don't need to bring a camera tomorrow.
>
> **Singlish:** Tomorrow don't need bring camera.

#### G2. Zero Copula [Hard, Light+]

Drop "is/am/are/was/were" before adjectives and adjective phrases. Also drop between nouns
and locatives when context is clear.

> **Standard:** This house is very nice.
>
> **Singlish:** Dis house very nice.

> **Standard:** That lady is his wife.
>
> **Singlish:** Dat one his wife lah.

> **Standard:** His house is in Toa Payoh.
>
> **Singlish:** His house in Toa Payoh.

> **Standard:** I'm so naughty.
>
> **Singlish:** I damn naughty.

#### G3. Drop or Reduce Articles [Hard, Light+]

Articles (a, an, the) are largely optional in Singlish. Drop most of them. Occasionally keep
"the" for emphasis or when needed for clarity.

> **Standard:** I like to read a storybook. The library has many books.
>
> **Singlish:** I like to read storybook. Library got many book.

> **Standard:** Does your computer have a virus or not?
>
> **Singlish:** Your computer got virus or not?

#### G4. Optional Tense Marking [Hard, Light+]

Past tense is optional. Keep it for irregular verbs and "-ed" pronounced as a separate
syllable (/ɪd/), but drop it elsewhere — especially for extended-duration actions.
Use "already" or "liao" for perfective aspect instead of English perfect tenses.

> **Standard:** I went to Orchard Road yesterday.
>
> **Singlish:** I go Orchard Road yesterday.

> **Standard:** He has been talking for so long and never stopped.
>
> **Singlish:** He talk so long, never stop.

> **Standard:** Your ice cream has melted.
>
> **Singlish:** Your ice cream melt already.

> **Standard:** I've already eaten.
>
> **Singlish:** I eat liao.

#### G5. Drop Plural Marking [Soft, Medium+]

Plural "-s" is optional. Drop it on most nouns, especially after numerals or quantifiers
where plurality is already obvious. Occasionally hypercorrect with "furnitures" or "stuffs."

> **Standard:** This one costs only ten cents.
>
> **Singlish:** This one ten cent only.

> **Standard:** There are three students.
>
> **Singlish:** Got three student.

#### G6. PRO-Drop (Omit Subject) [Hard, Medium+]

Drop the subject/topic when it's clear from context, as in Chinese and Malay.

> **Standard:** This isn't good.
>
> **Singlish:** No good lah.

> **Standard:** Why didn't they come?
>
> **Singlish:** How come never come leh?

> **Standard:** You can't just go around doing whatever you want.
>
> **Singlish:** Cannot anyhow go like dat one leh.

#### G7. "Or Not" and "Is It" Questions [Hard, Medium+]

Form yes-no questions with "or not" (neutral) or "is it" (implies surprise/confirmation).
Avoid English subject-auxiliary inversion for casual questions — just add a rising particle.

> **Standard:** Do you want this book?
>
> **Singlish:** You want this book or not?

> **Standard:** Is that possible?
>
> **Singlish:** Can or not?

> **Standard:** They didn't study? (No wonder they failed!)
>
> **Singlish:** They never study, is it?

> **Standard:** Does this bus have air conditioning?
>
> **Singlish:** This bus got air-con or not?

#### G8. "Never" as Negative Past [Hard, Medium+]

Use "never" where Standard English uses "didn't." The verb stays in base form.

> **Standard:** Why didn't you submit your homework today?
>
> **Singlish:** How come today you never hand in homework?

> **Standard:** Why didn't he pay just now?
>
> **Singlish:** How come he never pay just now?

---

### Discourse Particles（語氣詞）

Particles are the soul of Singlish. They attach to sentence-final position, convey pragmatic
meaning, and **retain their tones** regardless of the sentence. Use them generously but
appropriately — each has a specific function.

**Combination rule: One sentence-final particle per sentence.** Do not stack "lah lor" or
"leh sia" at the end. The only exception is "ah" used as a mid-sentence topic marker
(e.g., "This boy ah, always so rude one!") — "ah" marks the topic, "one" closes the sentence.
Choose the single particle that best fits the sentence's pragmatic intent.

#### D1. Lah — Solidarity and Softening [Hard, Light+]

The most iconic Singlish particle. Softens commands, signals reassurance, expresses mild
impatience, or builds rapport.

**Constraint: Lah CANNOT appear in yes-no questions.** Use meh, hor, or ah instead.

> **Softening:** Drink lah! *(just drink it)*
>
> **Reassurance:** Dun worry, he can one lah. *(don't worry, he's capable)*
>
> **Impatience:** Eh, hurry up lah.
>
> **Emphasis:** I dun have lah!

#### D2. Lor — Resignation and Obviousness [Hard, Light+]

Signals "it is what it is" — resignation, dismissiveness, or stating the obvious.

> **Resignation:** Kay lor, you go and do what you want.
>
> **Obvious inference:** Dun have work to do, den go home lor.
>
> **Agreement:** Ya lor. *(yeah, that's right)*

#### D3. Meh — Skeptical Questions [Hard, Light+]

Forms questions that express surprise or disbelief — "I thought otherwise."

> **Skepticism:** They never study meh? *(I thought they did)*
>
> **Disbelief:** Really meh? *(Is that really so?)*
>
> **Surprise:** You don't like dat one meh?

#### D4. Hor — Seeking Agreement [Soft, Medium+]

Draws the listener's attention, asks for consent or agreement. Also used as a narrative
connector ("and then...").

> **Agreement-seeking:** This shopping centre very nice hor?
>
> **Narrative:** Then hor, another person came out.
>
> **Realization:** Oh yah hor! *(Oh, right!)*

#### D5. Leh — Softening [Soft, Medium+]

Softens commands, requests, or complaints that would otherwise sound brusque.

> **Soft request:** Gimme leh. *(please give it to me)*
>
> **Complaint:** The ticket seriously ex leh. *(tickets are expensive, argh)*
>
> **Mild objection:** You call her walk there, very far leh.

#### D6. Ah — Topic Marker and Filler [Hard, Medium+]

Inserted between topic and comment to set up the sentence. Rising tone marks questions;
mid-level tone marks genuine inquiries.

> **Topic marker:** This boy ah, always so rude one!
>
> **Rhetorical question:** How come like dat one ah?
>
> **Warning:** Dun play play ah! *(don't mess around!)*

#### D7. One — Characteristic Emphasis [Hard, Medium+]

Placed at sentence-end to emphasize that something is characteristically or inherently so.
Analogous to Cantonese 嘅/㗎 or Mandarin 的.

> **Characteristic:** He never go school one. *(he's the type who doesn't go)*
>
> **Inherent:** Is like dat one. *(it is how it is)*
>
> **Emphasis:** I do everything by habit one.

#### D8. Wat — Reminding or Contradicting [Soft, Heavy]

Reminds the listener of something they should already know, or contradicts their assumption.

> **Reminder:** But he very good at Maths wat. *(you should know this)*
>
> **Contradiction:** I never punch him wat! *(it's not my fault)*
>
> **Assertion:** The food there not bad wat. Can try lah.

---

### Vocabulary Patterns（詞彙模式）

#### V1. "Got" for Existence and Possession [Hard, Medium+]

Map Chinese 有 onto "got" for both "there is/are" and "have/has." "Where got" expresses
emphatic denial.

> **Standard:** Are there any questions?
>
> **Singlish:** Got question?

> **Standard:** There were so many people at Marina Bay Sands!
>
> **Singlish:** Marina Bay Sands got so many people one!

> **Standard:** That's not true! / There isn't any!
>
> **Singlish:** Where got!?

#### V2. "Can" as Universal Response [Hard, Medium+]

Use "can" as a standalone question and answer. The negative is "cannot." Repetition adds
emphasis: "Can, can!" = absolutely.

> **Standard:** Could you give that to me?
>
> **Singlish:** Gimme can?

> **Standard:** Sure!
>
> **Singlish:** Can!

> **Standard:** No way.
>
> **Singlish:** Cannot.

> **Standard:** Is that okay?
>
> **Singlish:** Can or not?

#### V3. "Kena" Passive for Negative Events [Hard, Medium+]

Use "kena" (from Malay) as a passive marker for bad things. Never use kena with positive
outcomes (unless sarcastic).

> **Standard:** He was scolded.
>
> **Singlish:** He kena scold.

> **Standard:** Be careful or you'll be punished.
>
> **Singlish:** Dun listen, later you kena punish.

> **Standard:** I got fined. What can I do?
>
> **Singlish:** Kena fined lor, what to do?

#### V4. Verb Reduplication [Soft, Medium+]

Repeat verbs twice for brief actions, three times for extended ones. Conveys vividness
and casualness.

> **Standard:** Think about it briefly, then you'll find the answer.
>
> **Singlish:** You go think think a bit, maybe den you get answer.

> **Standard:** Want to go to Orchard for some shopping and sightseeing?
>
> **Singlish:** Want to go Orchard walk walk see see or not?

> **Standard:** Don't touch things randomly.
>
> **Singlish:** Don't anyhow touch here touch there leh.

#### V5. "Already" / "Liao" for Completion [Hard, Medium+]

Use "already" or Hokkien "liao" to mark completed actions or state changes. Replaces
English perfect tenses.

> **Standard:** We can't wait anymore, we have to go now.
>
> **Singlish:** Cannot wait any more, must go already.

> **Standard:** He has thrown it away.
>
> **Singlish:** He throw liao.

> **Standard:** My son is starting Primary One now.
>
> **Singlish:** My boy-boy going Primary One oreddy.

#### V6. Hokkien and Malay Loanwords [Hard, Medium+]

Sprinkle common loanwords naturally throughout. These are core Singlish vocabulary, not
exotica. Use a few well-placed loanwords per paragraph — cramming every word is unnatural.

**Core loanwords** (use freely at Medium+):

| Loanword | Meaning | Origin |
|----------|---------|--------|
| shiok | extremely enjoyable/satisfying | Malay |
| makan | eat | Malay |
| kiasu | afraid to lose out, FOMO | Hokkien |
| alamak | oh my god (surprise) | Malay |
| jialat | terrible, in deep trouble | Hokkien |
| paiseh | embarrassed, shy | Hokkien |
| sian | bored, tired of something | Hokkien |
| ex | expensive | English (clipping) |

**Extended loanwords** (use at Heavy, or sparingly at Medium when context fits):

| Loanword | Meaning | Origin |
|----------|---------|--------|
| kiasi | afraid to die, overly cautious | Hokkien |
| bojio | didn't invite (me) | Hokkien |
| ang moh | Caucasian/Westerner | Hokkien |
| kopitiam | coffee shop/hawker centre | Hokkien+Malay |
| boleh | can, able to | Malay |
| chope | reserve (a seat) | Singlish |
| atas | high-class, posh | Malay |
| blur | confused, clueless | English (semantic shift) |
| sabo | sabotage (verb, casual) | English (clipping) |
| lepak | hang out, relax | Malay |
| ponteng / pon | play truant, skip class | Malay |
| swaku | out of touch, old-fashioned | Hokkien |
| steady | impressive, cool, reliable | English (semantic shift) |

#### V6b. Semantic Shifts from Substrate Languages [Soft, Medium+]

Some English words shift meaning in Singlish due to Hokkien/Malay substrate influence.
Use these naturally — they are authentic Singlish, not errors.

- **"Borrow" = lend** — Hokkien 借 (chio̍h) means both borrow AND lend.
  "Eh, can borrow me your calculator?" = Can you lend me your calculator?
- **"Send" = accompany/take someone** — Hokkien 送 (sàng) means both send AND escort.
  "I send you to the airport lah." = I'll take you to the airport.
- **"Follow" = come along** — "Can I follow you?" = Can I come along with you?

#### V7. "Damn" as Intensifier [Soft, Medium+]

Use "damn" as a casual intensifier replacing "very" or "really." Also use "super," "sibei"
(Hokkien 死父, very), or "damn" + adjective without copula.

> **Standard:** The food is really good.
>
> **Singlish:** The food damn good sia.

> **Standard:** That's really expensive.
>
> **Singlish:** Wah, damn ex leh.

> **Standard:** He's incredibly capable.
>
> **Singlish:** He damn zai sia.

#### V8. "Den" / "Then" as Multi-Purpose Connector [Soft, Medium+]

Use "den" for "so/therefore," "after that," conditional "if...then," or to return an insult.

> **Standard:** I didn't do my homework, so I got scolded.
>
> **Singlish:** Never do homework den kena scold lor.

> **Standard:** I'll call you when I get home.
>
> **Singlish:** I go home liao den call you.

> **Standard:** (A: "You're stupid!") You're the stupid one!
>
> **Singlish:** You den stupid lah.

---

### Structure Patterns（結構模式）

#### S1. Sentence-Final "Like That" / "Lidat" [Soft, Heavy]

Append "like that" (often compressed to "lidat") to emphasize descriptions, adding vividness.

> **Standard:** He really seems pretty stupid.
>
> **Singlish:** He so stupid like that.

> **Standard:** He's really acting like a baby.
>
> **Singlish:** He acting like one-year-old baby like that.

> **Standard:** Why is he behaving this way?
>
> **Singlish:** Why he acting like dat?

#### S2. Exclamations and Interjections [Hard, Heavy]

Use Singlish exclamations for emotional color: "wah lau" (frustration/shock),
"alamak" (surprise), "aiyoh" (exasperation), "oi" (calling attention).

> **Frustration:** Wah lau! Teacher give so much homework!
>
> **Surprise:** Alamak, I forget bring wallet!
>
> **Exasperation:** Aiyoh, how come like dat one?
>
> **Attention:** Oi, you forgot give me my pencil!

#### S3. Spelling Conventions [Hard, varies by intensity]

Use Singlish spelling conventions to reflect pronunciation. Apply per intensity level:

| Standard | Singlish | Active from |
|----------|----------|-------------|
| don't | dun | Medium |
| that | dat | Medium |
| this | dis | Medium |
| them/then | den | Medium |
| what (particle) | wat | Medium |
| already | oreddy | Heavy |
| the | de | Heavy |
| brother | brudder | Heavy |
| friend | fren | Heavy |
| there | dere | Heavy |

**Light**: No spelling changes — keep standard orthography.
**Medium**: Only the 5 most common respellings (dun, dat, dis, den, wat).
**Heavy**: Full respelling table. Not every word needs respelling, but apply generously.

---

## Step 3: Produce Singlish Output

Apply the checklist to transform the entire text. Aim for a natural, consistent Singlish voice.

### Intensity Levels

Each rule is tagged with its minimum intensity (e.g., `[Hard, Light+]` = active from Light up;
`[Soft, Heavy]` = only in Heavy mode).

| Level | Active Rules | Effect |
|-------|-------------|--------|
| **Light** | G1-G4 (topic-comment, copula, articles, tense) + D1-D3 (lah, lor, meh). No spelling changes, no loanwords. | Reads like an educated Singaporean in casual mode. |
| **Medium** (default) | Light + G5-G8, D4-D7, V1-V8 (core loanwords, got, can, kena, reduplication), S3 basic spelling (dun, dat, dis, den, wat). | Clearly Singlish — particles in most sentences, common loanwords, topic-comment structure. |
| **Heavy** | All rules including D8, S1-S2 (lidat, exclamations), S3 full spelling, extended loanwords. | Reads like a kopitiam conversation — dense particles, frequent loanwords, basilectal spelling. |

If the user doesn't specify, use **Medium**.

### Input-Specific Handling

**English input → Singlish:**
1. Restructure sentences to topic-comment order where natural.
2. Drop copula, articles, tense marking, and plurals per the rules.
3. Add discourse particles to most sentences — choose the appropriate one for the pragmatic context.
4. Replace vocabulary with Singlish equivalents where fitting.

**Chinese input → Singlish:**
1. Translate to English first, but preserve Chinese sentence structure (topic-comment, serial verbs).
2. Apply all Singlish patterns — the Chinese structure naturally aligns with many Singlish features.
3. Add discourse particles and loanwords for authentic flavor.

---

## Step 4: Output

1. **File output:** Save to `_singlish` suffix (e.g., `article.md` → `article_singlish.md`).
   If no file was provided, output directly in conversation.
2. **Show 3-5 representative sentence pairs** comparing Original and Singlish versions.
3. **List applied patterns:** Note which major patterns (G/D/V/S) were most active.
4. **Loanword glossary:** Briefly list loanwords used with meanings (keep concise — one line each).

---

## Important Notes

- This is a **stylistic transformation tool** for creative, educational, and cultural purposes.
- Singlish is a **legitimate creole language** with systematic grammar, not random broken English.
  Treat it with linguistic respect.
- Do NOT produce offensive, racist, or demeaning content. The goal is authentic representation
  of a living language, not caricature.
- **Discourse particles are not random filler.** Each has specific pragmatic functions — use them
  appropriately. "Lah" is not a catch-all; "meh" only appears in skeptical questions; "lor"
  signals resignation; etc.
- **Kena is only for negative events** (unless being sarcastic). This is a hard rule.
- The **creole continuum** is real: not every Singaporean speaks the same Singlish. This skill
  targets the mesolectal-to-basilectal range for maximum distinctiveness.
- When in doubt about a particle, think: "What would a Singaporean auntie at the hawker centre
  say?" That's the register we're aiming for.
