---
name: wenyan-guwen
description: >
  Rewrite modern Chinese text into Tang-Song classical prose style (唐宋古文體),
  emulating the essay voice of 韓愈, 柳宗元, 歐陽修, and 蘇軾. Applies a 20-item
  checklist covering classical function words, single-character verbs, thesis-driven
  structure, varied rhythm, literary allusion, and register markers.
  Works on markdown files or inline text.
  Triggers on "/wenyan-guwen", "寫成古文", "寫成文言文", "用文言文寫", "古文體",
  "唐宋風格", "韓愈體", "蘇軾體", "classical Chinese prose", "Tang-Song style".
argument-hint: [file-path]
allowed-tools: Read, Write, Edit, Glob
---

# Wenyan-Guwen — 改寫為唐宋古文體

將現代中文改寫為唐宋古文運動風格的文言散文，追求「文以載道、氣韻生動」的行文質感。

代表作者：韓愈、柳宗元、歐陽修、蘇軾、曾鞏、王安石

## Arguments

- `$0` — (optional) Markdown or plain text file path. If omitted, ask for inline text.

## Step 1: Load the Text

- If `$0` is provided, read the file.
- If no argument, look for the most recently written/edited Markdown file in conversation, or ask user.

## Step 2: Scan & Assess

Read the full text. Identify:
1. The core argument or message (載道之旨).
2. Modern vocabulary and syntax that need classical transformation.
3. Passage structure — does it suit essay (論), preface (序), or record (記) form?

## Step 3: Apply Classical Prose Patterns

Apply the checklist below. Each item marked [Hard] must be applied; [Soft] items apply when natural.

---

### Checklist: Grammar Patterns (G: 語法句式)

#### G1. Topic-Comment Structure (主題—評論句式) [Hard]

Replace modern SVO with topic-comment or topic-predicate structure. Drop unnecessary subjects.

> **Before：** 學習這件事情是很重要的。
>
> **After：** 人非生而知之者，孰能無學？

> **Before：** 做老師是不容易的。
>
> **After：** 師之道，難矣。

---

#### G2. Classical Conditional & Causal (假設因果) [Hard]

Replace「如果…就」「因為…所以」with 苟…則、以…故、蓋…也、由…而…。

> **Before：** 如果不努力學習，就會落後。
>
> **After：** 苟不學，則殆矣。

> **Before：** 因為他不聽勸告，所以才失敗。
>
> **After：** 以其不從諫，故敗。

---

#### G3. Concessive & Adversative (讓步轉折) [Hard]

Replace「雖然…但是」with 雖…然…、雖…而…、然…。

> **Before：** 雖然我年紀大了，但是志向不減。
>
> **After：** 吾雖老矣，然志未衰。

> **Before：** 道理雖然很簡單，但是很少人做到。
>
> **After：** 理雖易明，而行之者寡。

---

#### G4. Varied Sentence Length (長短交錯) [Hard]

Consciously alternate short punchy clauses (4-6 chars) with longer flowing ones (10-15 chars). This is the signature rhythm of 古文 that distinguishes it from 駢文.

> **Before：** 秋天到了，天氣變冷了，樹葉也掉了，看起來很蕭條。
>
> **After：** 秋至。天肅而葉零，蕭然有悲意。

> **Before：** 山很高，水很深，路很遠，去的人很少。
>
> **After：** 山高水深，路遙行者稀。

---

#### G5. Classical Rhetorical Questions (設問反問) [Soft]

Use 豈…乎、何…之有、孰…與…、庸…乎 for rhetorical emphasis.

> **Before：** 難道不值得深思嗎？
>
> **After：** 豈不令人深省乎？

> **Before：** 有什麼困難的呢？
>
> **After：** 何難之有？

---

#### G6. Parallel But Free (駢散結合) [Soft]

Use occasional parallel clauses for emphasis, but do NOT lock into rigid 4-6 couplets. The 古文 aesthetic mixes balanced pairs with free-flowing prose.

> **Before：** 有的人富有但不快樂，有的人貧窮但很滿足。
>
> **After：** 富者未必樂，貧者未必戚。然世人汲汲於富貴，不亦惑乎？

---

#### G7. Judgment with 也 (判斷句) [Hard]

Replace copula「是」with classical judgment patterns: X者Y也、X也、非X也。

> **Before：** 這是天下最大的禍患。
>
> **After：** 此天下之大患也。

> **Before：** 他不是普通人。
>
> **After：** 非常人也。

---

### Checklist: Vocabulary Patterns (V: 詞彙用字)

#### V1. Classical Particles (語氣詞替換) [Hard]

Systematically replace modern particles:
- 了 → 矣
- 嗎 → 乎
- 啊/吧 → 哉 / 也 / 焉
- 呢 → 耶 / 邪
- 的 → 之（structural）
- 地 → (delete or restructure)
- 得 → (restructure)

> **Before：** 這件事太嚴重了啊！
>
> **After：** 此事甚重矣哉！

> **Before：** 你覺得這樣好嗎？
>
> **After：** 子以為善乎？

---

#### V2. Classical Function Words (虛詞替換) [Hard]

Core substitutions:
- 的 → 之
- 在 → 於
- 和/跟 → 與
- 從 → 自
- 用/拿 → 以
- 但是 → 然
- 所以 → 故
- 就 → 則/乃/遂
- 還 → 猶/尚
- 又 → 復/亦

> **Before：** 在這個時代，和朋友一起從困境中走出來。
>
> **After：** 於此世，與友自困厄中出。

---

#### V3. Single-Character Verbs (動詞精簡) [Hard]

Replace bisyllabic verbs with single-character equivalents:
- 學習 → 學
- 思考 → 思
- 知道 → 知
- 認為 → 以為 / 謂
- 說話 → 言
- 聽到 → 聞
- 看見 → 見
- 擔心 → 慮 / 憂
- 喜歡 → 好
- 明白 → 明 / 曉

> **Before：** 我們應該認真思考這個問題。
>
> **After：** 吾人當深思此事。

---

#### V4. Classical Pronouns (代詞替換) [Soft]

- 我 → 吾 / 余 / 予
- 你 → 子 / 君 / 汝
- 他 → 其 / 彼
- 我們 → 吾輩 / 吾人
- 自己 → 己

Use sparingly — 古文 frequently drops pronouns entirely (see G1).

> **Before：** 我自己認為我們都應該努力。
>
> **After：** 余以為吾輩當勉之。

---

#### V5. Anti-Ornamental Vocabulary (去藻飾) [Hard]

Reject flowery or unnecessarily complex vocabulary. The 古文運動 explicitly opposed 駢文 ornamentation. Choose plain, direct words.

> **Before：** 在璀璨奪目的星空下，沉浸於無邊無際的遐想之中。
>
> **After：** 仰望星空，遐思無窮。

> **Before：** 光輝燦爛的偉大事業在蓬勃發展。
>
> **After：** 事業方興。

---

#### V6. Classical Negation (否定詞) [Hard]

- 不 → 不 / 弗
- 沒有 → 未 / 無
- 不要 → 毋 / 勿
- 不能 → 不能 / 莫能
- 不是 → 非

> **Before：** 不要因為小事而忘記大事。
>
> **After：** 勿以小失大。

---

#### V7. Remove Modern Connective Padding (去連詞贅語) [Hard]

Delete or compress「雖然…但是…」「不但…而且…」「因為…所以…」into classical connective flow. 古文 relies on semantic connection, not explicit connectors.

> **Before：** 不但要注重學習，而且要注重品德。
>
> **After：** 學不可廢，德尤當修。

> **Before：** 雖然他很有才華，但是品德不好，所以大家不喜歡他。
>
> **After：** 彼雖有才，德行不修，人皆惡之。

---

### Checklist: Style Patterns (S: 風格修辭)

#### S1. Thesis-Driven Opening (文以載道) [Hard]

Every essay must open with a clear thesis or proposition. Do not meander into the topic.

> **Before：** 在現代社會中，教育是一個非常值得討論的重要議題。隨著時代的進步，我們越來越重視這個問題。
>
> **After：** 古之學者必有師。

> **Before：** 關於朋友之間的信任，我想說幾點看法。
>
> **After：** 友者，信之本也。

---

#### S2. Historical Allusion (用典) [Soft]

Where appropriate, substitute modern examples or abstract statements with references to historical events, classical texts, or well-known figures.

> **Before：** 一個人如果太自大，遲早會失敗。
>
> **After：** 驕者必敗，項羽之覆可鑒也。

---

#### S3. Natural Flow Over Rigid Structure (氣韻生動) [Hard]

The defining aesthetic of 古文. Prose should feel like natural speech elevated to literary form — not a mechanical exercise in parallelism. Let the argument drive the structure, not the other way around.

This means:
- Vary paragraph length
- Let some points land in 4 characters, others in 20
- Use parallel structure for emphasis, then break it
- Do not force every sentence into a mold

> **Before (機械並列)：** 山高矣，水深矣，路遠矣，人稀矣。
>
> **After (氣韻生動)：** 山高水深，路遙行者稀。嗚呼，誰與歸？

---

#### S4. Emotional Resonance (情理交融) [Soft]

The best 古文 weaves personal feeling into rational argument. 歐陽修 and 蘇軾 are masters of this. Where the source text has emotional content, let it breathe — do not strip it for the sake of terseness.

> **Before：** 我聽到母親去世的消息，非常悲傷，回想起她生前對我的關愛，更加難過。
>
> **After：** 聞母之訃，悲不自勝。追念生前撫育之恩，涕泗交零。

---

#### S5. Essay-Appropriate Closure (收束有力) [Soft]

End with a punchy conclusion — a judgment, a rhetorical question, or a resonant image. Do not trail off or add unnecessary summary.

> **Before：** 總而言之，我認為這是一個非常重要的問題，值得我們所有人深思。
>
> **After：** 是可忽乎？

---

### Checklist: Register Markers (R: 時代標記)

#### R1. Eliminate 把/被 Constructions [Hard]

把字句 and 被字句 are post-Tang vernacular developments. Replace:
- 被 → use 為…所… or restructure as active
- 把 → restructure with 以 or direct object fronting

> **Before：** 他被敵人抓住了。
>
> **After：** 為敵所執。

> **Before：** 他把書還給了老師。
>
> **After：** 以書歸師。

---

#### R2. Classical Time & Place Markers [Soft]

Replace modern time expressions with classical forms:
- 那時候 → 是時 / 當是時
- 後來 → 既而 / 已而
- 在那裡 → 於彼
- 現在 → 今

> **Before：** 後來他終於成功了。
>
> **After：** 既而竟成。

---

#### R3. Classical Sentence-Final Patterns [Hard]

Ensure sentences end with proper classical patterns, not modern trailing particles:
- Statement: …也 / …矣 / …焉
- Question: …乎 / …哉 / …邪
- Exclamation: …哉 / …矣夫
- Imperative: …可也 / …其…乎

> **Before：** 這就是所謂的天命吧。
>
> **After：** 此所謂天命也。

---

## Step 4: Rewrite

Apply all checklist items to produce a complete rewrite. Follow these principles:

### Rewriting Principles

1. **載道為先** — Identify the core message first. Every sentence should serve it.
2. **精簡為尚** — Classical Chinese is inherently compressed. The output will be shorter than the input. This is expected.
3. **散中有駢** — Use occasional parallel structure for emphasis, but keep the overall texture free-flowing.
4. **以意逆志** — Understand the author's intent before transforming. Do not mechanically substitute characters.
5. **留有餘韻** — Let some things go unsaid. Classical prose trusts the reader.
6. **去陳言** — 韓愈's principle: eliminate cliches and stale expressions. Seek fresh phrasing.

---

## Step 5: Authenticity Audit

### Pass 1 — Pattern Re-scan

Re-read the rewritten text against the checklist above. Check for:
- Surviving modern vocabulary (especially 連接詞 and 把/被)
- Inconsistent register (mixing 古文 and modern within a sentence)
- Missed opportunities for compression

### Pass 2 — Gut Check

Read the whole piece aloud (mentally). Ask:
- Does it flow like 韓愈 or 蘇軾, or does it feel stilted?
- Are there anachronisms? (Modern concepts phrased in ways that feel jarring)
- Is the rhythm varied (short + long), or monotonously uniform?

Fix any remaining issues.

---

## Step 6: Output

1. **Save to new file** with `_guwen` suffix (e.g., `article.md` → `article_guwen.md`). If user explicitly requests in-place edit, overwrite.
2. Show 3-5 most representative before/after pairs.
3. State which patterns were most heavily applied.

---

## Important Notes

- This skill is a **style transformation tool**, not a content generator. Preserve the original meaning.
- Do **NOT** add information, arguments, or examples not present in the original.
- Classical Chinese is naturally more compressed — the output **will be shorter** than the input. This is expected, not a loss.
- This is **stylistic approximation**, not philologically rigorous reconstruction. The goal is to evoke the *feel* of Tang-Song 古文, not to produce a text that would fool a specialist.
- When the source contains modern technical terms with no classical equivalent (e.g., 半導體, 演算法), **keep the term** and transform the surrounding prose.
- 古文 ≠ 駢文. Do NOT produce rigid 4-6 parallel couplets throughout. The whole point of the 古文運動 was to break free from that rigidity.
- Pair with `wenyan-hanwei` (historical narrative), `wenyan-xianqin` (pre-Qin philosophical), or `wenyan-huaben` (vernacular fiction) for other classical styles.
