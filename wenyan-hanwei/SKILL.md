---
name: wenyan-hanwei
description: >
  Rewrite modern Chinese text into Han-Wei historical narrative prose style
  (漢魏史傳體), emulating the biographical voice of 司馬遷《史記》, 班固《漢書》,
  and 陳壽《三國志》. Applies a 20-item checklist covering biographical formula,
  chronological narration, dialogue as characterization, precise action verbs,
  implicit moral judgment, and historian's commentary.
  Works on markdown files or inline text.
  Triggers on "/wenyan-hanwei", "史傳體", "史記風格", "漢書體", "三國志體",
  "historical narrative", "biographical prose", "Han-Wei style".
argument-hint: [file-path]
allowed-tools: Read, Write, Edit, Glob
---

# Wenyan-Hanwei — 改寫為漢魏史傳體

將現代中文改寫為漢魏史傳體歷史敘事散文，追求「以事見人、寓褒貶於敘事」的行文質感。

代表作者：司馬遷、班固、陳壽、裴松之、范曄

## Arguments

- `$0` — (optional) Markdown or plain text file path. If omitted, ask for inline text.

## Step 1: Load the Text

- If `$0` is provided, read the file.
- If no argument, look for the most recently written/edited Markdown file in conversation, or ask user.

## Step 2: Scan & Assess

Read the full text. Identify:
1. The subject(s) — who is being written about? Determine if the text suits 本紀, 列傳, or 載記 form.
2. The key events and deeds that define the subject's character (以事見人).
3. Modern vocabulary, syntax, and narrative structure that need classical transformation.

## Step 3: Apply Historical Narrative Patterns

Apply the checklist below. Each item marked [Hard] must be applied; [Soft] items apply when natural.

---

### Checklist: Grammar Patterns (G: 語法句式)

#### G1. Biographical Opening Formula (傳記起首) [Hard]

Open with the classical identification formula: 「X者，Y人也」, establishing the subject's name, native place, and courtesy name. This is the signature opening of every 列傳.

> **Before：** 張明是一個來自河南的年輕人，他從小就很聰明。
>
> **After：** 張明者，河南人也。少聰敏，有異才。

> **Before：** 李偉出生在四川成都，他的父親是一位老師。
>
> **After：** 李偉，蜀郡成都人也。父為郡學師。

Note: do NOT invent courtesy names (字) or other biographical details not present in the original.

---

#### G2. Chronological Narration with Temporal Markers (紀事時序) [Hard]

Structure the narrative chronologically using classical temporal markers: 初 (at first), 既而 (subsequently), 及 (when it came to), 後 (later), 是時 (at that time), 久之 (after a long while), 未幾 (before long).

> **Before：** 他一開始很順利，後來遇到了困難，最後終於成功了。
>
> **After：** 初，事頗順。既而遇阻，久之，竟以功成。

> **Before：** 過了一段時間，他被調到另一個部門。
>
> **After：** 久之，徙為別部。

---

#### G3. Classical Passive with 為…所… (被動句式) [Hard]

Replace modern 被字句 with 為…所… passive construction. This is the standard passive form in Han-Wei prose.

> **Before：** 他被上司陷害了。
>
> **After：** 為上官所構陷。

> **Before：** 城市被敵軍佔領了。
>
> **After：** 城為敵所據。

---

#### G4. Object Fronting and Verb-Final (賓語前置) [Hard]

In negation, questions, and emphasis, front the object before the verb. This is a hallmark of classical syntax.

> **Before：** 他什麼都不怕。
>
> **After：** 無所畏也。

> **Before：** 沒有人能阻擋他。
>
> **After：** 莫之能禦。

---

#### G5. Concise Scene-Setting (簡筆白描) [Hard]

Set scenes with minimal but vivid detail. Han-Wei prose never dwells on extended description — it selects one or two sharp images, then moves on.

> **Before：** 那天晚上下著大雨，天很黑，風也很大，整個城市都籠罩在一片恐怖的氣氛之中。
>
> **After：** 是夜，大雨，風甚暴。城中皆恐。

> **Before：** 到了冬天，天氣非常寒冷，士兵們穿的衣服很薄，糧食也快吃完了。
>
> **After：** 時冬月，士卒衣單糧盡。

---

#### G6. Historian's Evaluative Comment (論贊體) [Soft]

End with a historian's commentary in the style of 太史公曰 or 贊曰. This provides explicit moral judgment on the subject's life and deeds.

> **Before：** 總的來說，他是一個很有才華但結局悲慘的人。
>
> **After：** 贊曰：明才兼文武，志略超群，然不能容物，終以取禍。惜哉。

> **Before：** 回顧他的一生，他對國家的貢獻是不可忽視的。
>
> **After：** 論曰：偉之功於國，不可謂不偉。然觀其行事，亦時有可議者焉。

---

### Checklist: Vocabulary Patterns (V: 詞彙用字)

#### V1. Precise Action Verbs (精確動詞) [Hard]

Replace vague modern verbs with the precise action verbs of historical prose. Each verb carries specific social and political meaning:
- 去/到 → 趨 (hurry to), 詣 (visit a superior), 之 (go to)
- 派 → 遣 (dispatch)
- 給予職位 → 拜 (appoint), 除 (assign), 擢 (promote), 遷 (transfer)
- 拜訪 → 謁 (formally call on)
- 打敗 → 破 (defeat in battle), 克 (take a city)
- 殺 → 殺 (neutral), 誅 (execute for justice), 弒 (murder a superior)
- 死 → 卒 (die, of officials), 薨 (die, of lords), 崩 (die, of emperors)

> **Before：** 他去見了將軍，將軍派他帶兵去攻打敵人。
>
> **After：** 詣將軍，將軍遣將兵擊之。

> **Before：** 他被升職了，調到了首都工作。
>
> **After：** 擢拜郎中，徙為京職。

---

#### V2. Classical Pronouns and Titles (稱謂代詞) [Hard]

Use appropriate pronouns and title conventions:
- 我 → 臣 (to ruler), 吾/余 (general)
- 你 → 公 (respectful), 君 (peer), 卿 (ruler to minister)
- 他 → 其 (possessive/subject), 之 (object)
- Refer to subjects by surname after first introduction
- Use 字 (courtesy name) in dialogue for peers

> **Before：** 皇帝對他說：「你做得很好。」
>
> **After：** 帝謂之曰：「卿之功，朕甚嘉之。」

> **Before：** 他跟朋友說：「我覺得這樣做不對。」
>
> **After：** 謂其友曰：「吾以為此非善策也。」

---

#### V3. Implicit Moral Judgment Through Word Choice (春秋筆法) [Hard]

Choose words that carry embedded moral evaluation, following the 春秋 tradition of praise-blame through diction. The same event can be described with entirely different moral weight:

- 殺 (neutral kill) vs 誅 (righteous execution) vs 弒 (treasonous murder)
- 言 (speak, neutral) vs 諫 (remonstrate, loyal) vs 譖 (slander)
- 奔 (flee in defeat) vs 歸 (return in honor)
- 進 (advance, positive) vs 侵 (encroach, negative)

Use 春秋筆法 only when the original text already carries praise-blame intent. Do NOT impose moral judgment where the original is neutral.

> **Before：** 大臣被國王殺了。
>
> **After (if unjust)：** 王殺其大臣。
>
> **After (if treasonous)：** 大臣弒其君，國人誅之。

> **Before：** 他離開了那個國家。
>
> **After (if honorable)：** 遂歸。
>
> **After (if in disgrace)：** 出奔。

---

#### V4. Classical Function Words (虛詞替換) [Hard]

Core substitutions for narrative prose:
- 的 → 之
- 在 → 於
- 和 → 與
- 就/便 → 遂/乃
- 於是 → 乃/遂
- 因此 → 由是/以故
- 所以…是因為 → 所以…者，以…也
- 又 → 復/亦

> **Before：** 因為這件事，他的名聲在當地變得很大。
>
> **After：** 由是名聞於郡中。

---

#### V5. Classical Negation (否定詞) [Hard]

- 不 → 不/弗
- 沒有 → 未/無
- 不要 → 毋/勿
- 不能 → 莫能/不克
- 不是 → 非

> **Before：** 他不同意這個做法，也不願意參與。
>
> **After：** 不從，亦弗肯與焉。

---

#### V6. Classical Particles (語氣詞替換) [Hard]

Replace modern particles with classical sentence-final forms:
- 了 → 矣
- 嗎 → 乎
- 啊 → 哉
- 吧 → 也/焉
- 呢 → 邪/耶

Statement: …也 / …矣 / …焉
Question: …乎 / …哉 / …邪
Exclamation: …哉 / …矣夫

> **Before：** 這件事真的太不公平了吧！
>
> **After：** 此豈公乎哉！

---

### Checklist: Style Patterns (S: 風格修辭)

#### S1. Show Character Through Action (以事見人) [Hard]

The defining principle of 史傳體. Do NOT tell the reader someone is brave, wise, or cruel — SHOW it through a specific deed. Select incidents that crystallize character.

> **Before：** 他是一個非常勇敢的人，不管遇到什麼困難都不退縮。
>
> **After：** 嘗從征，陷陣中流矢，拔鏃復戰，左右皆壯之。

> **Before：** 他非常聰明，很小的時候就展現出超群的才能。
>
> **After：** 年十二，見郡守論事，應對如流。守大驚，以為非常兒也。

---

#### S2. Dialogue as Characterization (以言見性) [Hard]

Use direct speech (「X曰：」) to reveal character, not just to convey information. The best 史記 dialogues are miniature dramas. Keep dialogue terse and forceful.

> **Before：** 他非常生氣地告訴部下，如果不拼命戰鬥，大家都會死。
>
> **After：** 怒謂諸將曰：「今日之事，有進死而已。退者，斬！」

> **Before：** 他的妻子勸他放棄，但他說他絕不放棄。
>
> **After：** 妻諫止之。明曰：「丈夫處世，當建功立業，奈何效兒女子態邪？」

---

#### S3. Narrative Economy (敘事簡潔) [Hard]

Han-Wei prose achieves power through compression. An entire military campaign can be told in one sentence. Eliminate all redundancy, narrate only turning points.

> **Before：** 他帶著軍隊出發了，在路上走了很長時間，經歷了很多困難，最後終於到達了目的地，然後發動了攻擊，經過激烈的戰鬥，最終取得了勝利。
>
> **After：** 率師出征，行軍月餘，遂至，一戰破之。

> **Before：** 他在那個職位上做了三年，期間做了很多好事，老百姓都很感激他。
>
> **After：** 居官三年，甚有政聲。民為立碑。

---

#### S4. Date and Time in Classical Format (古典紀時) [Soft]

Use classical date/time conventions:
- 某年某月 → X年Y月 (reign year)
- 春天 → 春 / 是歲春
- 那天晚上 → 是夜
- 早上 → 旦 / 晨 / 平明
- 中午 → 日中
- 傍晚 → 薄暮 / 日昃

> **Before：** 在建安五年的秋天，曹操帶著軍隊出發。
>
> **After：** 建安五年秋，操率師以出。

---

#### S5. Indirect Commentary Through Juxtaposition (對比映襯) [Soft]

Rather than stating a moral lesson, place contrasting events or characters side by side and let the reader draw the conclusion. This is 司馬遷's signature technique.

> **Before：** 他本來很有權勢，但是最後卻落得很悲慘的下場，這說明權力是靠不住的。
>
> **After：** 方其盛也，一呼百諾，賓客盈門；及其敗，親故莫有顧者。

---

### Checklist: Register Markers (R: 時代標記)

#### R1. Eliminate 把/被 Constructions [Hard]

把字句 and 被字句 are post-Tang vernacular developments. Replace:
- 被 → use 為…所… or restructure as active voice
- 把 → restructure with 以 or direct verb-object

> **Before：** 他把敵人的使者送走了。
>
> **After：** 遣敵使還。

> **Before：** 他的計策被人識破了。
>
> **After：** 其謀為人所覺。

---

#### R2. Honorific and Humble Forms for Social Hierarchy (尊卑稱謂) [Hard]

Strictly observe social hierarchy in language:
- Emperor: 上、帝、天子; dies = 崩; decrees = 詔、敕
- Lords/Princes: 王、侯; die = 薨
- Officials: 公、卿; die = 卒
- Commoners: die = 死
- Self-deprecation to superiors: 臣、愚臣、末將

> **Before：** 國王死了以後，他的兒子繼位。
>
> **After：** 王薨，子立。

> **Before：** 他向皇帝報告了這件事。
>
> **After：** 上疏言狀。帝覽之。

---

#### R3. Eliminate Modern Connective Padding (去現代連詞) [Hard]

Delete or compress「雖然…但是…」「不但…而且…」「因為…所以…」into classical connective flow. Han-Wei prose relies on sequential narration and semantic adjacency, not explicit logical connectors.

> **Before：** 雖然他非常有才華，但是因為性格太過剛直，所以得罪了很多人。
>
> **After：** 有才略，然性剛直，多忤於人。

> **Before：** 不但百姓支持他，而且軍隊也願意聽他的命令。
>
> **After：** 百姓歸心，將士用命。

---

## Step 4: Rewrite

Apply all checklist items to produce a complete rewrite. Follow these principles:

### Rewriting Principles

1. **以事見人** — Show character through deeds, not adjectives. Let actions speak.
2. **敘事簡潔** — Every word must earn its place. An entire life can fit in a few hundred characters.
3. **寓褒貶於敘事** — Embed moral judgment in word choice and event selection, not explicit commentary.
4. **以言見性** — Use dialogue to reveal personality. The best lines are the ones only that character would say.
5. **詳略得當** — Dwell on pivotal moments, compress routine years. Not all events deserve equal space.
6. **善用對比** — Juxtapose rise and fall, virtue and vice. Let contrast do the moral work.

---

## Step 5: Authenticity Audit

### Pass 1 — Pattern Re-scan

Re-read the rewritten text against the checklist above. Check for:
- Surviving modern vocabulary (especially 把/被 and modern connectives)
- Inconsistent register (mixing 史傳體 and modern Chinese within a sentence)
- Missing biographical formula or temporal markers
- Vague verbs where precise ones exist (e.g., 去 instead of 趨/詣/之)

### Pass 2 — Gut Check

Read the whole piece aloud (mentally). Ask:
- Does it flow like 史記 or 漢書, or does it feel stilted?
- Are characters revealed through their actions and words, or merely described?
- Is the hierarchy of death/title terms consistent throughout?
- Does the rhythm feel like connected narrative, not a list of facts?

Fix any remaining issues.

---

## Step 6: Output

1. **Save to new file** with `_hanwei` suffix (e.g., `article.md` → `article_hanwei.md`). If user explicitly requests in-place edit, overwrite.
2. Show 3-5 most representative before/after pairs.
3. State which patterns were most heavily applied.

---

## Important Notes

- This skill is a **style transformation tool**, not a content generator. Preserve the original meaning and events.
- Do **NOT** add historical events, deeds, or dialogue not present or implied in the original.
- Classical Chinese is naturally more compressed — the output **will be shorter** than the input. This is expected, not a loss.
- This is **stylistic approximation**, not philologically rigorous reconstruction. The goal is to evoke the *feel* of 史記 and 漢書, not to produce a text that would fool a specialist.
- When the source contains modern technical terms with no classical equivalent (e.g., 半導體, 演算法), **keep the term** and transform the surrounding prose.
- 史傳體 is **narrative prose** about people and events. It is NOT argumentative (古文) or philosophical (先秦). If the source text is an opinion essay with no biographical subject, suggest `wenyan-guwen` instead.
- The 春秋筆法 (praise-blame through diction) should be used judiciously. Do not force moral judgment where the original text is neutral.
- Pair with `wenyan-guwen` (Tang-Song argumentative essay), `wenyan-xianqin` (pre-Qin philosophical), or `wenyan-huaben` (vernacular fiction) for other classical styles.
