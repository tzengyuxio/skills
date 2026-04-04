---
name: wenyan-huaben
description: >
  Rewrite modern Chinese text into Song-Ming-Qing vernacular fiction style
  (話本小說體 / 章回小說體), emulating the storyteller's voice of 水滸傳,
  三國演義, 紅樓夢, and 金瓶梅. Applies a 20-item checklist covering
  storyteller's frame, classical-vernacular code-switching, formulaic
  transitions, embedded poetry, and chapter-return structure.
  Works on markdown files or inline text.
  Triggers on "/wenyan-huaben", "話本體", "說書體", "水滸傳風格",
  "三國演義體", "章回小說", "vernacular fiction", "storyteller style".
argument-hint: [file-path]
allowed-tools: Read, Write, Edit, Glob
---

# Wenyan-Huaben — 改寫為話本小說體

將現代中文改寫為宋元明清話本小說 / 章回小說的敘事風格，追求「說書人開口、看官側耳」的臨場質感。

代表作品：《水滸傳》《三國演義》《紅樓夢》《金瓶梅》《西遊記》《儒林外史》

**核心特徵：這不是純文言，而是文白夾雜的「說書人敘事體」——敘述偏半文言，對話偏白話口語，兩者交替構成獨特的語域張力。**

## Arguments

- `$0` — (optional) Markdown or plain text file path. If omitted, ask for inline text.

## Step 1: Load the Text

- If `$0` is provided, read the file.
- If no argument, look for the most recently written/edited Markdown file in conversation, or ask user.

## Step 2: Scan & Assess

Read the full text. Identify:
1. The narrative situation — how many characters, what events, what scenes?
2. Whether the text suits a single scene (折), a full chapter (回), or an excerpt.
3. Opportunities for storyteller's frame, scene transitions, and embedded verse.
4. Which characters need epithets and how dialogue should be attributed.

## Step 3: Apply Vernacular Fiction Patterns

Apply the checklist below. Each item marked [Hard] must be applied; [Soft] items apply when natural.

---

### Checklist: Grammar Patterns (G: 語法句式)

#### G1. Storyteller's Opening Frame (說書人起頭) [Hard]

Every passage must open with a storyteller's formulaic lead-in. This is the signature of 話本: a narrator directly addressing an audience.

Choose from:
- 話說… (the most common)
- 卻說… (switching to another thread)
- 且說… (continuing a thread)
- 單表… (singling out one character)

> **Before：** 那天早上，張三出門去了。
>
> **After：** 話說張三那日清晨起來，收拾停當，出門而去。

> **Before：** 另一方面，李四也在準備。
>
> **After：** 卻說李四那邊，也在收拾行裝，準備動身。

---

#### G2. Scene-Shift Formulas (場景轉換) [Hard]

When switching between characters, locations, or time, use storyteller's transition formulas instead of modern paragraph breaks:

- 卻說那邊… / 再說…
- 按下不表，單說…
- 且不說…，只說…
- 花開兩朵，各表一枝

> **Before：** 我們先不說他，來看看另一邊的情況。
>
> **After：** 按下張三不表。且說那邊李四，自從別後，一路奔波。

> **Before：** 同時，在京城裡，王五也聽到了消息。
>
> **After：** 花開兩朵，各表一枝。卻說京城之中，王五早已聞得此信。

---

#### G3. Classical-Vernacular Code-Switching (文白夾雜) [Hard]

This is the defining texture of 話本小說. Narration uses semi-classical constructions; dialogue uses colloquial speech. The two registers alternate, creating a deliberate tension.

**Narration** (semi-classical): use 且、遂、乃、方才、只見、忽聞.
**Dialogue** (colloquial): use 你、我、怎的、休要、卻是、也罷.

> **Before：** 他看到了那個人，就說：「你怎麼在這裡？」
>
> **After：** 那人定睛觀看，只見一條大漢立在面前。便開口道：「你怎的在此？」

> **Before：** 她很生氣地回答：「我不想再見到你了。」
>
> **After：** 那小姐聽了，柳眉倒豎，杏眼圓睜，喝道：「休要再來見我！」

---

#### G4. Direct Speech with Classical Markers (對話標記) [Hard]

Replace modern speech markers with 話本 conventions:

- 「說」→ 道 / 言道 / 說道 / 開口道
- 「回答」→ 答道 / 回言道 / 應聲道
- 「大叫」→ 喝道 / 大喝道 / 叫道
- 「小聲說」→ 低聲道 / 附耳道

Speech markers always follow the pattern: [character] + [manner] + 道：

> **Before：** 他大聲說：「不要跑！」
>
> **After：** 那人大喝一聲道：「休走！」

> **Before：** 她小聲回答：「我知道了。」
>
> **After：** 那小姐低聲應道：「奴家知道了。」

---

#### G5. Suspense & Cliff-hanger Formulas (懸念公式) [Hard]

Use traditional suspense formulas at passage breaks and endings:

- 欲知後事如何，且聽下回分解
- 畢竟不知…，且聽下回分解
- 正是：[七言對句]。畢竟…如何，且聽下回分解
- 未知…，且看下文分解

**Judgment call**: use「且聽下回分解」only at mid-story chapter breaks where the story truly continues. For a **complete story** or **single-chapter piece**, close with「正是：[對句]」or a moral couplet instead — do NOT use「下回分解」when there is no next chapter.

> **Before：** 這件事後來怎樣了呢？我們下次再說。（mid-story break）
>
> **After：** 畢竟不知那人性命如何，且聽下回分解。

> **Before：** 這個故事就到這裡結束了。（story complete）
>
> **After：** 正是：世人偏愛差不多，到頭方知認真難。

---

#### G6. 把/被 Mixed with Classical Passives (兼用把被與古式) [Soft]

Unlike pure 古文 which eliminates 把/被, 話本小說 **both** classical and vernacular forms coexist. Use 把/被 in dialogue and colloquial narration; use 為…所… or active restructuring in formal narration passages.

> **Before：** 他被那個人打了一頓。(narration)
>
> **After：** 卻被那廝一頓好打。

> **Before：** 他被敵人俘虜了。(formal narration)
>
> **After：** 為敵所擒。

---

### Checklist: Vocabulary Patterns (V: 詞彙用字)

#### V1. Character Epithets (人物稱謂) [Hard]

Replace modern names and pronouns with 話本 epithet conventions:

- 他/她 → 那人 / 此人 / 那漢 / 那廝 / 那婦人 / 那小姐
- Named characters → epithet + name: 好漢武松 / 員外西門慶 / 小姐林黛玉
- Self-reference → 小人 / 在下 / 奴家 / 小的 / 灑家 / 某
- Respectful address → 官人 / 員外 / 恩公 / 大官人 / 姐姐 / 娘子

> **Before：** 他走過來問她。
>
> **After：** 那大漢走將過來，向那婦人問道。

> **Before：** 「我不知道，」她說。
>
> **After：** 那小姐搖頭道：「奴家實是不知。」

---

#### V2. Semi-Classical Vocabulary (半文言詞彙) [Hard]

Replace modern vocabulary with the characteristic semi-classical word stock of 話本:

- 很/非常 → 甚是 / 好生 / 十分
- 怎麼辦 → 如何 / 怎生 / 怎的
- 那個人 → 那廝 / 那人 / 那漢
- 就 → 便 / 遂 / 乃
- 馬上 → 當下 / 即時 / 登時
- 算了 → 也罷 / 罷了
- 大約 → 約莫 / 大約
- 一會兒 → 一盞茶功夫 / 片刻 / 少頃
- 這樣 → 如此 / 恁地 / 這般
- 趕快 → 快些 / 速速 / 急急

> **Before：** 他非常生氣，馬上就衝了過去。
>
> **After：** 那人甚是惱怒，登時便搶將過去。

> **Before：** 等了一會兒，他覺得算了。
>
> **After：** 等了一盞茶功夫，那人心下思量：也罷。

---

#### V3. Vivid Action Verbs (動作動詞) [Hard]

話本小說 has a rich tradition of physical action verbs that are far more vivid than modern equivalents:

- 走 → 行 / 趕 / 奔
- 跑 → 奔走 / 飛也似走
- 拿 → 提 / 掣 / 綽
- 看 → 觀看 / 定睛看 / 打量
- 打 → 一拳打去 / 掄起…打將過來
- 喝酒 → 篩酒 / 吃酒 / 飲酒
- 吃飯 → 吃些酒食 / 用飯
- 來/去 → 走將來 / 奔將去 / 趕將過來

> **Before：** 他拿起刀衝了過去。
>
> **After：** 那漢掣出腰刀，搶將過去。

> **Before：** 他喝了幾杯酒。
>
> **After：** 篩了三五碗酒吃了。

---

#### V4. Archaic Measure Words & Time Expressions (量詞與時間) [Soft]

Use period-appropriate measure words and time expressions:

- 一會兒 → 一盞茶功夫 / 半晌
- 幾天 → 三五日
- 很久 → 多時 / 良久
- 一間房 → 一間客房 / 一所院落
- 一把刀 → 一口刀 / 一柄刀
- 一匹馬 → 一匹快馬

> **Before：** 過了幾天，他才回來。
>
> **After：** 過了三五日，方才回來。

> **Before：** 等了很久都沒有消息。
>
> **After：** 等了多時，並無消息。

---

#### V5. Descriptive Set Phrases (程式化描寫) [Soft]

話本 uses formulaic description blocks for characters and settings:

- Appearance: 身長八尺、面如重棗、目若朗星、虎背熊腰
- Setting: 但見…、只見…、卻見…
- Weather/time: 時值…、正是那…時分、彼時…
- Emotion: 心下暗忖 / 心中大喜 / 面上變色 / 心中暗想

> **Before：** 那個人很高大，長得很威猛。
>
> **After：** 但見那人身長八尺，膀闊腰圓，面如鐵色，好一條壯漢。

> **Before：** 她心裡很高興。
>
> **After：** 那小姐聽罷，心中大喜，面上卻不露聲色。

---

#### V6. Classical Negation & Imperative (否定與祈使) [Hard]

Replace modern negation/imperative with 話本 vocabulary:

- 不要 → 休要 / 休得 / 莫要
- 別 → 休 / 莫
- 不能 → 不能夠 / 豈能
- 不是 → 不是 / 非是（narration）
- 快走 → 快些走 / 速速離去
- 住手 → 住手 / 罷手

> **Before：** 你不要亂說。
>
> **After：** 休得胡說！

> **Before：** 別走，聽我說完。
>
> **After：** 莫走！且聽我說個明白。

---

### Checklist: Style Patterns (S: 風格修辭)

#### S1. Chapter-Return Couplet Structure (回目) [Hard]

If the text is long enough to form a chapter, give it a 回目 — a title in parallel couplet form (usually two seven-character phrases).

Format: 第X回　[七字句]　[七字句]

> **Before：** 第三章：張三去找李四，路上遇到王五
>
> **After：** 第三回　張三訪友逢故識　王五攔路起風波

> **Before：** 第一章：故事開始
>
> **After：** 第一回　風雲際會群豪聚　龍虎交爭天下驚

---

#### S2. Embedded Poetry (有詩為證) [Soft]

Insert verse at dramatic or scenic moments using the formula「有詩為證」or「正是」followed by a quatrain (usually seven-character regulated verse).

The embedded verse should be **original doggerel-style poetry** (打油詩 / 通俗韻文) that fits the plot, not famous classical poems. 話本 verse is populist, not highbrow — rhyme and relevance matter more than strict prosody. Well-known proverbs or folk sayings (俗諺) are also appropriate.

> **Before：** 那個地方的風景很美。
>
> **After：** 那處風景甚好。有詩為證：
>
> 　山高水遠人煙少，竹密花深鳥語多。
> 　若非此處風光好，怎教行人懶過河。

> **Before：** 他感到人生無常。
>
> **After：** 那人感慨一回。正是：
>
> 　人事紛紛說到頭，誰人肯向死前休。
> 　黃金不是千年業，紅日能催兩鬢秋。

---

#### S3. Storyteller's Commentary (說書人插話) [Soft]

Break the fourth wall with narrator commentary — a hallmark of the 話本 tradition. This is what makes 話本 FUN: the storyteller is a character too.

- 看官聽說… / 列位看官…
- 原來這…有個緣故
- 你道是為何？
- 這也是…命中注定

> **Before：** 事情的原因是這樣的。
>
> **After：** 看官聽說，這裏頭卻有個緣故。

> **Before：** 你可能會問為什麼。
>
> **After：** 列位看官，你道是為何？

---

#### S4. Moral Commentary Through Narrator (敘事者議論) [Soft]

話本 narrators frequently offer moral judgments, often with a sigh or a proverb:

- 正所謂…
- 古人云…
- 常言道…
- 自古道…

> **Before：** 這就是不聽別人勸告的下場。
>
> **After：** 正所謂「忠言逆耳利於行」，奈何那人不聽，以致如此。

> **Before：** 做壞事一定會有報應。
>
> **After：** 自古道：「善惡到頭終有報，只爭來早與來遲。」信不虛也。

---

#### S5. Vivid Scene-Setting with 只見/但見 (場景描寫) [Hard]

Use 只見、但見、卻見 to introduce visual descriptions, creating cinematic "camera" effects:

> **Before：** 他進門後，看到屋裡坐著一個老人。
>
> **After：** 那人推門入去，只見堂上端坐著一位白髮老者，鶴髮童顏，精神矍鑠。

> **Before：** 外面下著大雪，非常冷。
>
> **After：** 掀開簾子看時，但見外面紛紛揚揚，下著一天大雪，好不寒冷。

---

### Checklist: Register Markers (R: 時代標記)

#### R1. Eliminate Modern Connectives (去除現代連接詞) [Hard]

Replace modern logical connectors with 話本 narrative flow:

- 因為…所以 → 只因…以致 / 皆因…故此
- 如果…就 → 若是…便 / 倘若…卻
- 雖然…但是 → 雖是…卻 / 雖然…奈何
- 不但…而且 → 不惟…更兼 / 非但…又且

> **Before：** 因為天氣太熱了，所以大家都不想出門。
>
> **After：** 只因天氣炎熱，眾人皆不願出門。

> **Before：** 如果你不同意，我就自己去。
>
> **After：** 你若是不肯同去，我便自家前往。

---

#### R2. Period-Appropriate Address & Self-Reference (時代稱謂) [Hard]

Ensure all forms of address match the 話本 register:

**Self-reference (by social status):**
- Commoner male → 小人 / 小的 / 在下
- Monk → 灑家 / 小僧 / 貧僧
- Woman → 奴家 / 妾身
- Official → 下官 / 本官

**Address (by social status):**
- Respectful male → 官人 / 大官人 / 員外 / 恩公
- Female → 娘子 / 姐姐 / 小姐
- Monk → 師父 / 長老
- Rude → 那廝 / 潑賊 / 匹夫

> **Before：** 「我覺得你說得對。」他對她說。
>
> **After：** 那人拱手道：「娘子說得是，小人再無異議。」

> **Before：** 「你這個壞人！」她罵道。
>
> **After：** 那婦人指著罵道：「你這潑賊！」

---

#### R3. Avoid Anachronistic Vocabulary (避免穿越詞彙) [Hard]

Remove vocabulary that would break the 話本 illusion:

- 電話/手機 → 書信 / 差人傳話
- 汽車 → 馬 / 車轎
- 公司/辦公室 → 店鋪 / 衙門 / 府上
- 網路/社群 → (restructure entirely)

When the source contains inherently modern concepts with no period equivalent, **keep the concept and note the anachronism** rather than force an awkward substitution. The storyteller can acknowledge it: 「列位看官，此物雖未見於古，然此處姑且道來。」

> **Before：** 他開車去公司上班。
>
> **After：** 那人騎了快馬，往衙門裏辦事去了。

> **Before：** 她打電話告訴他這個消息。
>
> **After：** 那小姐急急修書一封，差人送去，報與那人知道。

---

## Step 4: Rewrite

Apply all checklist items to produce a complete rewrite. Follow these principles:

### Rewriting Principles

1. **說書為魂** — You are a storyteller addressing an audience. Every sentence should carry the rhythm of oral narration, as if spoken aloud in a teahouse.
2. **文白交織** — Narration leans semi-classical; dialogue leans colloquial. This deliberate code-switching IS the style. Do not flatten into pure classical or pure vernacular.
3. **鋪陳有度** — 話本 is more expansive than 古文. Descriptions can be lavish, action sequences detailed, dialogue extended. The output may be LONGER than the input. This is expected.
4. **套語生輝** — Formulaic phrases (話說、卻說、有詩為證) are not lazy writing — they are structural elements that signal genre. Use them generously but not mechanically.
5. **人物見性** — Characters reveal personality through dialogue register, epithets, and action. Give each character a distinct voice.
6. **懸念勾連** — Always leave the audience wanting more. Use cliff-hangers, rhetorical questions, and deferred revelations.

---

## Step 5: Authenticity Audit

### Pass 1 — Pattern Re-scan

Re-read the rewritten text against the checklist above. Check for:
- Missing storyteller's frame (especially at opening and scene transitions)
- Modern connectives or vocabulary that survived the rewrite
- Dialogue that sounds too literary (should be colloquial) or narration that sounds too modern (should be semi-classical)
- Missing character epithets (bare pronouns 他/她 instead of 那人/那漢)

### Pass 2 — Voice Check

Read the whole piece aloud (mentally), as if performing it to an audience. Ask:
- Does it sound like a storyteller in a teahouse, or a textbook?
- Is the code-switching between narration and dialogue natural?
- Are there anachronisms that break the illusion?
- Do the 套語 (formulaic phrases) appear at the right structural moments?
- Would a reader of 水滸傳 or 三國演義 recognize this as the same register?

Fix any remaining issues.

---

## Step 6: Output

1. **Save to new file** with `_huaben` suffix (e.g., `article.md` → `article_huaben.md`). If user explicitly requests in-place edit, overwrite.
2. Show 3-5 most representative before/after pairs.
3. State which patterns were most heavily applied.

---

## Important Notes

- This skill is a **style transformation tool**, not a content generator. Preserve the original meaning and plot.
- 話本小說體 is **NOT pure classical Chinese**. It is a deliberate blend of classical and vernacular registers. Do not over-classicize — that would destroy the style.
- Unlike 古文 which compresses, 話本 often **expands**. The output may be longer than the input — this is expected. Storytellers elaborate, describe, and digress.
- The storyteller's voice is a **character** in its own right. It comments, teases, moralizes, and addresses the audience directly. This fourth-wall-breaking is a feature, not a bug.
- When the source contains modern technical terms with no period equivalent (e.g., 半導體, 演算法), **keep the term** and let the storyteller acknowledge the anachronism, or restructure the surrounding narrative to accommodate it.
- Do not confuse 話本 with 古文 or 駢文. The registers are fundamentally different. 話本 is performative oral narrative; 古文 is written essay; 駢文 is ornamental parallel prose.
- Pair with `wenyan-guwen` (Tang-Song essay), `wenyan-hanwei` (historical narrative), or `wenyan-xianqin` (pre-Qin philosophical) for other classical styles.
