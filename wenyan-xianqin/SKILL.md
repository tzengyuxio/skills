---
name: wenyan-xianqin
description: >
  Rewrite modern Chinese text into Pre-Qin philosophical prose style (先秦諸子體),
  emulating the aphoristic voice of 論語, 孟子, 莊子, 韓非子, and 左傳. Applies a
  20-item checklist covering extreme terseness, single-character words, subject
  dropping, classical particles, rhetorical question patterns, and parable-driven
  argumentation.
  Works on markdown files or inline text.
  Triggers on "/wenyan-xianqin", "先秦體", "諸子體", "論語體", "莊子體",
  "Pre-Qin style".
argument-hint: [file-path]
allowed-tools: Read, Write, Edit, Glob
---

# Wenyan-Xianqin — 改寫為先秦諸子體

將現代中文改寫為先秦諸子散文風格，追求「辭約義豐、一字千金」的極致簡鍊。

代表文本：《論語》《孟子》《莊子》《韓非子》《左傳》《老子》《荀子》

## Arguments

- `$0` — (optional) Markdown or plain text file path. If omitted, ask for inline text.

## Step 1: Load the Text

- If `$0` is provided, read the file.
- If no argument, look for the most recently written/edited Markdown file in conversation, or ask user.

## Step 2: Scan & Assess

Read the full text. Identify:
1. The core insight or teaching (微言大義).
2. Modern vocabulary and syntax that need radical compression.
3. Whether the text suits aphorism (語錄), disputation (論辯), parable (寓言), or chronicle (記事) form.

## Step 3: Apply Pre-Qin Philosophical Patterns

Apply the checklist below. Each item marked [Hard] must be applied; [Soft] items apply when natural.

---

### Checklist: Grammar Patterns (G: 語法句式)

#### G1. Judgement with 也, Not 是 (也字判斷) [Hard]

Pre-Qin Chinese had NO copula 是. All judgements use the pattern 「X者Y也」「X，Y也」「非X也」. Eliminate every copular 是.

> **Before：** 仁愛是人類最重要的美德。
>
> **After：** 仁者，人之大德也。

> **Before：** 這就是治國的根本道理。
>
> **After：** 治國之本也。

---

#### G2. Radical Subject Dropping (極致省略主語) [Hard]

Pre-Qin prose drops subjects far more aggressively than any later period. If the subject is inferable from context, DELETE it. A sequence of clauses sharing one subject states it only once — or not at all.

> **Before：** 孔子說：「我每天都會反省自己三次。」
>
> **After：** 子曰：「日三省。」

> **Before：** 君子知道什麼是對的，小人只知道什麼有利。
>
> **After：** 君子喻於義，小人喻於利。

---

#### G3. Topic-Comment with Zero Copula (主題—述語) [Hard]

Pre-Qin syntax is purely topic-comment. State the topic, then comment directly. No linking verb, no padding.

> **Before：** 關於政治的要點，最重要的在於贏得人民的信任。
>
> **After：** 政者，民信之。

> **Before：** 音樂的功能是調和人的情感。
>
> **After：** 樂，和情也。

---

#### G4. Classical Conditional & Causal (假設因果) [Hard]

Replace 如果…就 / 因為…所以 with 苟…則、故、是以、以…故. Pre-Qin often omits the conditional marker entirely — juxtaposition implies causation.

> **Before：** 如果名分不正確，說的話就不會順暢。
>
> **After：** 名不正，則言不順。

> **Before：** 因為他自己品行端正，所以不需要發布命令，事情自然就能辦好。
>
> **After：** 其身正，不令而行。

---

#### G5. Parallel Compression (對偶壓縮) [Hard]

Balance clauses to identical character counts. Pre-Qin parallelism is tighter than any later period — 4:4, 3:3, even 2:2. Each half must mirror the other in structure.

> **Before：** 知道的人不如喜歡的人，喜歡的人又不如享受其中的人。
>
> **After：** 知之者不如好之者，好之者不如樂之者。

> **Before：** 在上位的人如果喜歡禮，老百姓就沒有人敢不恭敬。
>
> **After：** 上好禮，民莫敢不敬。

---

#### G6. Rhetorical Question Patterns (反問定式) [Soft]

Use 不亦…乎、何…之有、豈…哉、孰…與…、安…、惡…. These are the signature rhetorical forms of Pre-Qin — use them to replace modern rhetorical questions.

> **Before：** 有朋友從遠方來，難道不是一件很快樂的事嗎？
>
> **After：** 有朋自遠方來，不亦樂乎？

> **Before：** 怎麼可能會有什麼困難的呢？
>
> **After：** 何難之有？

---

### Checklist: Vocabulary Patterns (V: 詞彙用字)

#### V1. Single-Character Words Throughout (單音節詞) [Hard]

Pre-Qin vocabulary is overwhelmingly monosyllabic. Every bisyllabic word must be challenged — most can be reduced to one character:
- 國家 → 國
- 學習 → 學
- 知道 → 知
- 思考 → 思
- 聽到 → 聞
- 看見 → 見
- 說話 → 言
- 擔心 → 憂
- 明白 → 知 / 明
- 喜歡 → 好 / 悅
- 選擇 → 擇
- 努力 → 勉

> **Before：** 我們應該認真學習並且努力思考。
>
> **After：** 學而思。

> **Before：** 孔子覺得非常高興。
>
> **After：** 子悅。

---

#### V2. Classical Particles (語氣詞) [Hard]

Pre-Qin particles are polysemous, each covering multiple modern functions:
- 也 — judgement, mild assertion, pause
- 矣 — completed action, new situation, exclamation
- 乎 — question, exclamation, preposition
- 哉 — strong exclamation, rhetorical question
- 焉 — "there / in it / how", combines 於+之
- 耳 — "merely, that's all"
- 夫 — sentence-initial topic marker, or final exclamation

> **Before：** 這件事已經結束了啊！
>
> **After：** 事畢矣夫！

> **Before：** 不過如此罷了。
>
> **After：** 如是而已耳。

---

#### V3. Classical Pronouns (代詞) [Hard]

- 我 → 吾 / 余 / 予
- 你 → 汝 / 爾 / 子 / 女
- 他/它 → 其 / 彼
- 自己 → 己
- 誰 → 孰
- 什麼 → 何
- 哪裡 → 安 / 惡 / 焉
- 這 → 此 / 是（指示詞，非繫詞）
- 那 → 彼

Drop pronouns whenever possible (see G2). When retained, use single characters only.

> **Before：** 你自己不想要的東西，不要強加給別人。
>
> **After：** 己所不欲，勿施於人。

---

#### V4. Classical Function Words (虛詞) [Hard]

Core substitutions:
- 的 → 之
- 在 → 於
- 和/跟 → 與
- 用/拿 → 以
- 從 → 自
- 就 → 則 / 乃
- 所以 → 故 / 是以
- 卻/但是 → 而

> **Before：** 用道德來治理國家，就好像北極星在它的位置上，所有的星星都圍繞著它。
>
> **After：** 為政以德，譬如北辰，居其所而眾星共之。

---

#### V5. Classical Negation (否定詞) [Hard]

Pre-Qin negation is richer than any later period:
- 不 — general negation
- 弗 — "not" (with implicit object)
- 未 — "not yet"
- 毋/勿 — prohibitive "do not"
- 莫 — "none / nobody / do not"
- 非 — "is not / not"
- 無 — "there is no"
- 微 — "were it not for" (counterfactual)

> **Before：** 不要擔心別人不了解你自己。
>
> **After：** 勿患人之不己知。

> **Before：** 沒有人能夠阻止它。
>
> **After：** 莫之能禦。

---

#### V6. Remove ALL Modern Connective Padding (去連詞) [Hard]

Pre-Qin prose uses almost no multi-syllable connectives. 因為…所以, 雖然…但是, 不但…而且, 如果…就 — ALL must go. Replace with juxtaposition, 而, 則, or nothing.

> **Before：** 雖然學習了但是沒有思考，就會迷惘；雖然思考了但是沒有學習，就會空虛危險。
>
> **After：** 學而不思則罔，思而不學則殆。

---

#### V7. Eliminate 把/被 Constructions (去把被句) [Hard]

把 and 被 as grammatical markers did not exist in Pre-Qin. Restructure:
- 被 → passive implied by context, or 見…、為…所…
- 把 → direct verb-object, or 以 + object

> **Before：** 他被小人陷害了。
>
> **After：** 見陷於小人。

> **Before：** 我把這件事告訴了他。
>
> **After：** 以告之。

---

### Checklist: Style Patterns (S: 風格修辭)

#### S1. Aphoristic Brevity (格言凝鍊) [Hard]

Every sentence should feel like it could be carved in stone. If a thought takes more than 8 characters, ask whether it can be split into two 4-character statements. The ideal unit is 4-8 characters.

> **Before：** 聰明的人喜歡水，仁慈的人喜歡山。聰明的人活潑好動，仁慈的人沉靜安穩。
>
> **After：** 知者樂水，仁者樂山。知者動，仁者靜。

> **Before：** 一個人做事如果只求差不多，最終會害了自己。
>
> **After：** 苟且者，自賊也。

---

#### S2. Parable & Analogy (寓言取譬) [Soft]

Where abstract argument dominates, consider replacing with a concrete image or micro-parable — the signature move of 莊子 and 韓非子.

> **Before：** 人的知識是有限的，但是世界上需要學習的東西是無限的。用有限的生命去追求無限的知識，是很危險的。
>
> **After：** 吾生也有涯，而知也無涯。以有涯隨無涯，殆已。

> **Before：** 不要用固定不變的方法去處理不斷變化的情況。
>
> **After：** 刻舟求劍，舟行而劍不行。

---

#### S3. Dialogue Markers (對話標記) [Soft]

Pre-Qin philosophical texts are built on dialogue. Use「X曰：」for speech, and the concise call-and-response rhythm of 論語:「問…」「答…」.

> **Before：** 有學生問孔子什麼是仁。孔子回答說：「愛人。」又問什麼是知。孔子回答說：「知人。」
>
> **After：** 樊遲問仁。子曰：「愛人。」問知。曰：「知人。」

---

#### S4. Layered Meaning (微言大義) [Soft]

The best Pre-Qin prose carries meaning beyond the surface. Let compression create ambiguity that rewards re-reading. Do not over-explain.

> **Before：** 我每天用三件事來反省自己：幫別人做事有沒有盡心？和朋友來往有沒有守信用？老師傳授的學業有沒有認真複習？
>
> **After：** 日三省吾身：為人謀而不忠乎？與朋友交而不信乎？傳不習乎？

---

### Checklist: Register Markers (R: 時代標記)

#### R1. NO Multi-Syllable Conjunctions (禁多音節連詞) [Hard]

This is the single most important register marker. Pre-Qin had NONE of these: 因為、所以、雖然、但是、而且、或者、如果、即使、不但、因此、然而、可是. Their presence instantly breaks the register. Every one must be eliminated.

> **Before：** 因為教育不普及，所以很多人不知道禮義。然而如果能夠推行教化，即使是普通百姓也可以成為君子。
>
> **After：** 教不行，民不知禮義。苟行教化，則庶人可為君子。

---

#### R2. Classical Time & Place (時地詞) [Soft]

- 那時候 → 是時 / 當是時
- 後來 → 既而
- 從前 → 昔 / 昔者
- 現在 → 今
- 以前 → 先 / 曩
- 將來 → 後

> **Before：** 從前有一個農夫在田裡耕作。
>
> **After：** 昔者農人耕於田。

---

#### R3. Sentence Rhythm: 4-Character Base (四言為基) [Hard]

Pre-Qin prose gravitates toward 4-character phrases as the default rhythm unit, occasionally expanding to 5 or 6, contracting to 2 or 3. This 4-char pulse is the heartbeat of the style.

**Hard rule: each clause defaults to 4 characters. Clauses over 6 characters need strong justification. Clauses over 8 characters should almost never appear.**

> **Before：** 如果自己的行為端正，不用下命令事情也會被執行；如果自己的行為不端正，即使下了命令也沒有人會服從。
>
> **After：** 其身正，不令而行；其身不正，雖令不從。

> **Before：** 差不多先生的相貌，跟你跟我都差不多。（14字子句）
>
> **After：** 其貌與眾同。（5字）

---

## Step 4: Rewrite

Apply all checklist items to produce a complete rewrite. Follow these principles:

### Rewriting Principles

1. **一字千金** — Every character must earn its place. If it can be removed without losing meaning, remove it.
2. **辭約義豐** — Maximum meaning in minimum characters. **Target: output should be 30-50% of the input's character count.** If the output exceeds 50%, compression is insufficient — go back and cut harder.
3. **述而不論** — State; do not explain. Trust the reader to draw the inference.
4. **正言若反** — The most powerful statements often take paradoxical form (老子's signature).
5. **取譬明理** — When logic alone is dry, one concrete image outweighs ten abstract arguments.
6. **寓莊於諧** — Serious ideas can ride on playful or absurd examples (莊子's method).

### Target Quality: Complete Example

Below is a short passage rewritten in the target register — this is the level of compression and rhythm to aim for:

> **Modern (68 chars)：** 他是一個做事只求差不多的人。別人都說他看得開、想得通，認為他很有修養。但其實他只是懶惰和馬虎，最後因為這個態度而喪命。
>
> **先秦 (24 chars)：** 苟且者也。人以為達，實怠也。卒以此死。

Note: 24/68 ≈ 35% — within the target compression ratio.

---

## Step 5: Authenticity Audit

### Pass 1 — Pattern Re-scan

Re-read the rewritten text against the checklist above. Check for:
- Any surviving copula 是 (most common failure)
- Any multi-syllable conjunctions (因為, 所以, 雖然, 但是, etc.)
- Any 把/被 constructions
- Any bisyllabic words that could be monosyllabic — go sentence by sentence: if a sentence of 8 chars contains 2+ bisyllabic words, it has not been compressed enough
- Clauses exceeding 8 characters that could be split
- **Character count check**: count the total characters of the output vs input. If the ratio exceeds 50%, the rewrite needs further compression

### Pass 2 — Read-Aloud Test

Read the whole piece aloud (mentally). Ask:
- Does it sound like something from 論語 or 莊子, or does it sound like a modern student imitating classical Chinese?
- Is the rhythm rooted in 4-character phrases with natural variation?
- Are subjects dropped aggressively enough? (If you can point to who is doing what in every clause, you have not dropped enough.)
- Does it feel carved, not written?

Fix any remaining issues.

---

## Step 6: Output

1. **Save to new file** with `_xianqin` suffix (e.g., `article.md` → `article_xianqin.md`). If user explicitly requests in-place edit, overwrite.
2. Show 3-5 most representative before/after pairs.
3. State which patterns were most heavily applied.

---

## Important Notes

- This is the **most extreme compression** of all classical Chinese styles. Meaning WILL be compressed and some nuance may be lost. This is inherent to the style, not a defect.
- For most practical purposes (essays, proposals, formal writing), **`wenyan-guwen` (Tang-Song prose) is more appropriate**. Use this skill only when the Pre-Qin philosophical register is specifically desired.
- This is a **style transformation tool**, not a content generator. Preserve the original meaning to the extent the extreme compression allows.
- Do **NOT** add teachings, parables, or philosophical content not present in the original.
- When the source contains modern technical terms with no classical equivalent (e.g., 半導體, 演算法), **keep the term** and transform the surrounding prose.
- Pre-Qin prose ≠ poetry. Do NOT force rhyme or uniform line length. The rhythm is prose rhythm — regular but not rigid.
- 先秦諸子 each have distinct voices: 論語 is terse dialogue, 莊子 is imaginative parable, 韓非子 is sharp argument, 左傳 is laconic narrative. Match the sub-style to the source text's nature when possible.
- Pair with `wenyan-guwen` (Tang-Song essay), `wenyan-hanwei` (historical narrative), or `wenyan-huaben` (vernacular fiction) for other classical styles.
