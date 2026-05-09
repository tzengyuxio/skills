---
name: shanghainese
description: >
  Transform text into Shanghainese （上海話 / 滬語） — the Wu Chinese variety
  spoken in Shanghai, belonging to the Taihu subgroup （太湖片） of Wu （吳語）.
  Features Wu pronouns （儂/阿拉/伊/伊拉）, Wu negation （弗/勿/覅）, sentence-final
  particles （呃/嘞/伐/哦呦）, Wu adverbs （蠻/老/嘎）, signature lexicon
  （結棍/霞氣/嗲/戇/洋盤/淘漿糊/軋鬧猛/噶三胡）, cultural vocabulary
  （弄堂/石庫門/阿婆/爺叔/小囡）, and海派 register （派頭/有腔調）. Three
  intensity levels from light Wu-flavored Mandarin (sprinkled markers) up to
  heavy 滬語書寫 (in the manner of 金宇澄《繁花》).
  Useful for creative writing, cultural appreciation, language education, or
  dialogue craft.
  Triggers on "/shanghainese", "寫成上海話", "滬語化", "翻成上海話",
  "translate to shanghainese", "make it shanghainese", "上海話", "滬語",
  "吳語", "儂", "阿拉", "海派", "周立波", "繁花".
license: PolyForm Noncommercial 1.0.0
argument-hint: [file-path]
allowed-tools: Read, Write, Edit, Glob
---

# Shanghainese — 上海話 / 滬語

Transform text into Shanghainese （上海話 / 滬語） — the Wu Chinese variety
spoken in Shanghai, a member of the Taihu subgroup （太湖片） of Wu （吳語）.
Linguistically Wu is a sister group to Mandarin within Sinitic, not a Mandarin
subdialect; Shanghainese has its own pronouns, negation, particles, and
phonology. The result should read like 周立波《海派清口》台上的快口節奏、王
家衛《繁花》劇本的腔調，或是金宇澄小說裡那種以「滬語思維」寫成的書面語
——地道、有腔調，又不刻意誇張。

This skill targets the **written representation** of Shanghainese in Han
characters — not the IPA / 吳語拼音 phonetics, but the way Shanghainese surfaces
on the page. It exists on a continuum from Light (Mandarin backbone with a
few signature 滬語 markers) through Medium (sentence-final particles and
syntax in addition to lexicon) to Heavy (full 滬語書寫，《繁花》式對白風格）。

## A note on writing Shanghainese

Unlike Cantonese, written Shanghainese has not been fully standardised. Three
conventions coexist:

- **本字 (etymological characters)** — historically supported forms such as
  儂 / 阿拉 / 弗 / 伊 / 嘞 / 覅. Use these when available.
- **訓用字 (semantic borrowings)** — common but disputed forms such as 結棍
  (jié-gùn, "impressive") and 霞氣 (variants 嚇氣 / 下氣）. The skill picks
  the form most widely seen in print (《繁花》、海派清口、《新民晚報》等）.
- **借音字 / 不寫 (phonetic borrowing or omission)** — for words without an
  agreed character, prefer the most common print form rather than novel
  coinages.

When in doubt prefer the form found in 金宇澄《繁花》, 上海方言詞典（錢乃榮）,
or the 維基詞典「上海話」分類.

## Arguments

- `$0` — (Optional) Path to a markdown or text file. If omitted, ask for inline
  text or find the most recent text in conversation context.

## Step 1: Load the Text

- If `$0` is provided, read the file.
- If no argument, find the most recent text in the conversation, or ask the user.
- The input can be **Mandarin Chinese** (rewrite as Shanghainese), **any
  language** (translate to Shanghainese), or **English** (translate to
  Shanghainese).

## Step 2: Apply Shanghainese Patterns

Apply the rules below systematically. Goal: every paragraph should carry at
least one 滬語 marker — a Wu pronoun, a Wu negation, a sentence-final particle,
or a signature lexical item. Not every rule applies to every sentence — pick
what fits naturally.

### Soul clause — 吳語句法 + 標誌詞密度 [C-class Hard]

**Every output must satisfy all four conditions, regardless of intensity:**

1. **Pronoun replacement** — 你 → 儂；我們 → 阿拉；他/她 → 伊；他們 → 伊拉
   appears at least once where applicable.
2. **Negation replacement** — 不 → 弗 / 勿 (or 覅 for 不要） appears at least
   once.
3. **At least 3 signature 滬語 lexical items** drawn from V1-V3 below
   (e.g., 結棍 / 霞氣 / 嗲 / 戇 / 洋盤 / 淘漿糊 / 軋鬧猛 / 噶三胡 / 蠻 / 老 / 嘎）.
4. **At least one sentence-final particle** from 呃 / 嘞 / 啦 / 伐 / 呢 /
   哦呦 appears.

A passage that misses any of these four is **not Shanghainese** — re-edit
until all four conditions are met. (Exception: for very short input < 30 字
or single-line dialogue, conditions 3 may be relaxed to "at least 1
signature item.")

---

### Grammar Patterns（語法模式）

#### G1. 人稱代詞 — 儂 / 阿拉 / 伊 / 伊拉 [Hard, Light+]

| 普通話 | 上海話 | 備註 |
|---|---|---|
| 你 | 儂 | nong, 第二人稱單數 |
| 你們 | 㑚 / 儂篤 | naq；非正式書寫常作「儂搿幾個」「儂篤」 |
| 我 | 我 / 吾 | 單數通常仍寫「我」（讀 ngu）|
| 我們 | 阿拉 | 受寧波話影響的高頻詞，最具標誌性 |
| 他 / 她 | 伊 | yi |
| 他們 | 伊拉 | yi-laq |

> **Standard:** 你吃飯了嗎？我們等你呢。
>
> **Shanghainese:** 儂飯吃過了伐？阿拉等儂呢。

> **Standard:** 他不知道。
>
> **Shanghainese:** 伊弗曉得。

#### G2. 否定詞 — 弗 / 勿 / 覅 / 嘸沒 [Hard, Light+]

| 普通話 | 上海話 | 備註 |
|---|---|---|
| 不 | 弗 / 勿 | feq；最高頻否定 |
| 不要 | 覅 | viau，「弗要」合音字 |
| 沒 / 沒有 | 嘸沒 / 嘸 | m-meq |
| 不曾 | 朆 | fen |

> **Standard:** 你不要去。
>
> **Shanghainese:** 儂覅去。

> **Standard:** 我沒看見。
>
> **Shanghainese:** 我嘸沒看見。

#### G3. 句末助詞 — 呃 / 嘞 / 伐 / 啦 / 呢 / 哦呦 [Hard, Light+]

| 助詞 | 功能 | 典型用法 |
|---|---|---|
| 呃 | 對應普通話「的」（句末或定語）| 蠻好呃 / 我講呃 |
| 嘞 | 完成 / 變化（≈ 了）| 飯吃過嘞 / 走嘞 |
| 伐 | 是非疑問（≈ 嗎）| 好伐？ / 曉得伐？ |
| 啦 | 已然 / 提示 | 來啦 / 好啦 |
| 呢 | 進行 / 並列疑問 | 等儂呢 / 儂呢？ |
| 哦呦 | 驚嘆 / 不滿 / 訝異 | 哦呦，價鈿介貴！ |
| 是伐 | 確認反問 | 儂去呃，是伐？ |

> **Confirmation:** 儂曉得伐？
>
> **Surprise:** 哦呦，介結棍呃啦！
>
> **Completion:** 阿拉吃好嘞。

#### G4. 程度副詞 — 蠻 / 老 / 嘎 / 邪氣 [Hard, Light+]

| 普通話 | 上海話 | 用法 |
|---|---|---|
| 很 | 蠻 / 老 | 蠻好、老靈呃、老遠 |
| 非常 | 邪氣 / 老 | 邪氣好；「邪氣」較老派 |
| 那麼 / 這麼 | 嘎 / 介 | 嘎好、介結棍、介遠 |
| 多 / 很多 | 老多 / 蠻多 | |

> **Standard:** 這個東西很好吃。
>
> **Shanghainese:** 搿樣物事老好吃呃。

> **Standard:** 那麼遠你還去？
>
> **Shanghainese:** 嘎遠儂還要去？

#### G5. 動詞「拿」與「畀」結構 [Soft, Medium+]

上海話的處置與給予結構與普通話略異。

> **Standard:** 把它拿來。
>
> **Shanghainese:** 拿伊拿過來。 / 拿伊撥我。

> **Standard:** 給你看。
>
> **Shanghainese:** 撥儂看。

#### G6. 方位後置與「V 一 V」/「V 一記」 [Soft, Medium+]

動詞重疊或後綴「一記」「一歇」，表短時試探。

> **Standard:** 看一看。 / 試一試。
>
> **Shanghainese:** 看一看 / 看一記 / 看一歇。

> **Standard:** 等一下。
>
> **Shanghainese:** 等一歇 / 等一記。

#### G7. 「困覺去」「吃飯去」式動補後置 [Soft, Medium+]

動詞 + 賓語 + 趨向動詞，與普通話「去吃飯」順序顛倒。

> **Standard:** 我去睡覺。
>
> **Shanghainese:** 我困覺去。

> **Standard:** 他去吃飯了。
>
> **Shanghainese:** 伊吃飯去嘞。

#### G8. 「阿是 / 啊有」反問式 [Soft, Medium+]

句首「阿」+ 動詞 / 形容詞，構成反問或徵詢。

> **Standard:** 是嗎？
>
> **Shanghainese:** 阿是？

> **Standard:** 有沒有？
>
> **Shanghainese:** 啊有？

> **Standard:** 你知道嗎？
>
> **Shanghainese:** 儂阿曉得？

---

### Vocabulary Patterns（詞彙模式）

#### V1. 標誌詞 — 海派核心集 [Hard, Light+]

These are the most recognisable 滬語 markers — sprinkle them generously. They
are the lexical fingerprint of Shanghainese.

| 滬語 | 普通話 | 備註 |
|---|---|---|
| 結棍 | 厲害 / 棒 | jié-gùn，正面或感嘆皆可 |
| 霞氣 | 嚇人 / 噁心 / 過分 | 多形容讓人不舒服的場面 |
| 霞匹 | 討厭 / 討人嫌 | 與 霞氣 同源語感 |
| 嗲 | 可愛 / 嬌媚 / 美 | 對人可形容嬌、對物可形容好 |
| 戇 | 笨 / 傻 | gàng，常見「戇大」「戇度」|
| 洋盤 | 外行 / 容易上當 | 海派典型用語 |
| 淘漿糊 | 混 / 敷衍混過去 | tao-jiang-hu |
| 軋鬧猛 | 湊熱鬧 | 「軋」= 擠進去 |
| 噶三胡 / 嘎三胡 | 閒聊 | 一說源自 gossip |
| 賊忒兮兮 | 鬼鬼祟祟 | 形容人神色詭異 |
| 蠻 | 很 | 程度副詞，見 G4 |
| 老 | 很 | 同上 |
| 嘎 / 介 | 那麼 / 這麼 | 同上 |
| 物事 | 東西 | 文白讀皆有 |
| 搿 | 這 | 搿個 = 這個 |
| 迭 | 這 | 迭個 = 這個（書面常見變體）|
| 啥 / 啥物事 | 什麼 | |

#### V2. 文化詞 — 弄堂海派風物 [Hard, Light+]

| 滬語 | 意義 / 文化背景 |
|---|---|
| 弄堂 | 上海特有的里弄住宅街巷 |
| 石庫門 | 19 世紀末至 20 世紀初的代表性住宅形式 |
| 阿婆 | 老婦人（多指外祖母或鄰里長輩）|
| 爺叔 | 中年男性、叔伯輩；在《繁花》中為核心稱謂 |
| 阿爹 | 父親 / 祖父（依家族傳統）|
| 阿姆媽 | 母親 |
| 小囡 | 小孩 |
| 寧波幫 | 近代上海的寧波籍商業群體 |
| 跑街 | 商行外勤；引申為跑腿 |
| 白相 | 玩 |
| 上只角 / 下只角 | 上海舊時城區的雅俗地理區分 |
| 排骨年糕 / 生煎 / 大餅油條 | 海派飲食代表 |

#### V3. 海派評價詞 — 派頭與腔調 [Hard, Medium+]

| 滬語 | 意義 |
|---|---|
| 派頭 | 氣派、風範 |
| 有腔調 | 有風格、有氣質 |
| 紮台型 | 撐場面、有面子 |
| 拎得清 | 拎得清楚、識相、懂分寸 |
| 拎勿清 | 不識相、搞不清狀況 |
| 識相 | 會看臉色 |
| 適意 | 舒服、寫意 |
| 靈光 | 行、好用 |
| 勿來三 | 不行、不可以 |
| 好白相 | 好玩 |
| 老克勒 | 老派紳士、洋派老上海 |

#### V4. 普通話常用詞的滬語替換 [Hard, Light+]

| 普通話 | 上海話 |
|---|---|
| 吃 | 吃（讀 chiq）|
| 喝 | 吃（吃酒、吃茶）|
| 看 | 看 / 望 |
| 走 | 走 / 跑（跑路 = 走路）|
| 給 | 撥 |
| 拿 | 拿 |
| 知道 | 曉得 |
| 喜歡 | 歡喜 |
| 漂亮 | 好看 / 嗲 |
| 為什麼 | 為啥 / 做啥 |
| 怎麼 | 哪能 |
| 怎麼辦 | 哪能辦 |
| 哪裡 | 啥地方 / 哪能 |
| 現在 | 現在 / 眼門前 |
| 睡覺 | 困覺 |
| 起床 | 爬起來 |
| 回家 | 轉去 / 回去 |

#### V5. 上海話外來語 [Soft, Medium+]

上海開埠後吸收大量音譯詞，部分已進入普通話，部分仍是地方標記。

| 滬語 | 來源 / 對應 |
|---|---|
| 沙發 | sofa（先入滬語再進入普通話）|
| 司的克 | stick（手杖）|
| 派司 | pass（通行證）|
| 戇度 | "Don't"（一說源自英文）|
| 嘎三胡 | gossip |
| 噱頭 | 一說源自滑稽戲，海派標誌 |
| 老克勒 | "old class"（一說）|
| 大興 | "Dashing"（贗品、假貨）|
| 拉三 | lassie（女郎，含貶義，慎用）|

---

### Structure Patterns（句式 / 結構）

#### S1. 語序：賓語前置與時間後置 [Hard, Medium+]

上海話常將賓語前置或時間語放句末。

> **Standard:** 我吃過早飯了。
>
> **Shanghainese:** 我早飯吃過嘞。

> **Standard:** 我剛剛去了趟超市。
>
> **Shanghainese:** 我超市跑過一趟，剛剛。

#### S2. 反問句「阿是 / 是伐 / 阿曉得」 [Hard, Medium+]

> 阿是儂講呃？
>
> 儂阿曉得搿樁事體？
>
> 好伐？是伐？

#### S3. 「個」字定語結構 [Soft, Medium+]

「呃 / 個」用於定語連接，類似普通話「的」但更輕。

> **Standard:** 我說的就是這件事。
>
> **Shanghainese:** 我講呃就是搿樁事體。

#### S4. 感嘆詞與發語詞 [Hard, Light+]

| 詞 | 場合 |
|---|---|
| 哦呦 | 驚嘆 / 不滿 |
| 唉呀 | 不悅 / 撒嬌 |
| 嘖嘖嘖 | 嘆服 / 感慨 |
| 喔唷 | 痛感 / 強烈驚訝 |
| 嘎 | 詢問附和（「嘎，是伐？」）|

---

## Step 3: Produce Shanghainese Output

Apply the checklist to transform the entire text. Maintain a natural, consistent
滬語 voice at the chosen intensity. The Soul clause must hold across the whole
output, not just one sentence.

### Intensity Levels

Each rule is tagged with its minimum intensity (e.g., `[Hard, Light+]` = active
from Light up; `[Soft, Heavy]` = mainly Heavy).

| Level | Active Rules | Effect |
|---|---|---|
| **Light** | G1 （儂 / 阿拉 partial), G2 （弗 in fixed phrases), G4 （蠻 / 老）, V1 (3-5 標誌詞）, V2 （文化詞 if relevant), S4 （感嘆詞 selectively). 句法骨幹仍是普通話。 | 普通話讀者完全讀得懂，「上海味」靠詞彙與少量代詞點綴；像新民晚報副刊或半正式部落格。|
| **Medium** (default) | Light + G1 全（儂/阿拉/伊/伊拉）, G2 全（弗/覅）, G3 （句末助詞）, G5-G8 （拿 / 一記 / 困覺去 / 阿是）, V3-V4 （海派評價 + 詞彙替換）, V5 （外來語）, S1-S3. | 明顯滬語腔，句末助詞 + 部分句式吳語化；像周立波清口的書面化版本，或《愛情神話》式對白。|
| **Heavy** | All rules; 全篇滬語書寫，整段使用 G1-G8 與 V1-V5；趨向《繁花》小說式書面語，文白雜糅。 | 完整滬語書寫；普通話讀者讀來會有閱讀阻力，需要靠上下文猜測；金宇澄《繁花》風格。|

If the user doesn't specify, use **Medium**.

### Input-Specific Handling

**Mandarin input → Shanghainese:**
1. Replace pronouns (G1) and negations (G2) per intensity.
2. Add sentence-final particles (G3) to sentences that carry pragmatic
   meaning — questions take 伐 / 阿是；completions take 嘞；exclamations take
   哦呦 + 啦.
3. Swap adverbs (G4) — 很 → 蠻 / 老；那麼 / 這麼 → 嘎 / 介.
4. Replace common verbs and content words (V4) and inject 標誌詞 (V1) where
   they fit the meaning.
5. At Medium+, apply syntactic transforms (G5-G8, S1-S3).
6. At Heavy, apply liberally — the resulting text should look more like
   Shanghainese than Mandarin.

**Non-Mandarin input → Shanghainese:**
1. Translate to Standard Mandarin first, preserving meaning.
2. Apply Shanghainese transforms as above.

---

## Step 4: Output

1. **File output:** Save to `_shanghainese` suffix (e.g., `article.md` →
   `article_shanghainese.md`). If no file was provided, output directly in
   conversation.
2. **Show 3-5 representative sentence pairs** comparing Original and
   Shanghainese.
3. **List applied patterns:** Note which major pattern groups (G/V/S) were
   most active.
4. **Glossary:** List 標誌詞 / 文化詞 / 外來語 used, with普通話 equivalents.

---

## 21-Item Checklist

四類 21 條，編號用於 demo 標註。Soul clause 為 C-class Hard，全文必達。

### Core / 靈魂條款 (C)

- **C-01 [Hard]** 人稱代詞替換：儂（你） / 阿拉（我們）至少各一次出現。
- **C-02 [Hard]** 否定詞替換：弗 / 勿 / 覅 至少出現一次。
- **C-03 [Hard]** 標誌詞密度：V1-V3 中至少 3 個出現。
- **C-04 [Hard]** 句末助詞：呃 / 嘞 / 伐 / 啦 / 呢 / 哦呦 至少出現一次。
- **C-05 [Hard]** 不刻板印象：避免「上海人精明 / 排外 / 拜金」類戲仿。

### Grammar (G)

- **G-01 [Hard, Light+]** 人稱代詞系統完整（伊 / 伊拉 在 Medium+ 補上）。
- **G-02 [Hard, Light+]** 否定詞分工：弗（一般）、覅（不要）、嘸沒（沒有）。
- **G-03 [Hard, Light+]** 句末助詞按語用功能配對。
- **G-04 [Hard, Light+]** 程度副詞替換：蠻 / 老 / 嘎 / 介。
- **G-05 [Soft, Medium+]** 拿 / 撥 結構於處置與給予句中使用。
- **G-06 [Soft, Medium+]** 「V 一記 / 一歇」短時體出現。
- **G-07 [Soft, Medium+]** 「困覺去」式動補後置出現。
- **G-08 [Soft, Medium+]** 「阿是 / 啊有 / 阿曉得」反問式出現。

### Vocabulary (V)

- **V-01 [Hard, Light+]** 標誌詞至少 3 個（結棍 / 霞氣 / 嗲 / 戇 / 洋盤等）。
- **V-02 [Hard, Light+]** 文化詞按題材使用（弄堂 / 石庫門 / 爺叔 / 小囡）。
- **V-03 [Hard, Medium+]** 海派評價詞：派頭 / 有腔調 / 紮台型 / 拎得清。
- **V-04 [Hard, Light+]** 普通話常用詞替換：曉得 / 歡喜 / 困覺 / 撥 / 啥。
- **V-05 [Soft, Medium+]** 上海話外來語：沙發 / 派司 / 嘎三胡 / 大興。

### Meta (M)

- **M-01 [Hard]** 標點：CJK 句內全形，不夾入半形句號逗號。
- **M-02 [Hard]** 不混入粵語字（嘅 / 咗 / 佢 / 嗰）；上海話與粵語是不同語族。
- **M-03 [Soft]** Heavy 模式可以呈現《繁花》式不分行對白，但 Medium / Light 維持一般段落格式。

---

## Important Notes

- This is a **stylistic transformation tool** for creative, educational, and
  cultural purposes.
- Shanghainese is a **legitimate Wu Chinese variety** （吳語太湖片蘇滬嘉小片）,
  not "broken Mandarin." Wu and Mandarin are sister groups within Sinitic;
  Shanghainese has its own pronouns （儂/阿拉/伊）, negation （弗/覅）, tones (5
  tones, reduced from 8), and lexicon. Treat with linguistic respect.
- **Avoid stereotypes.** Do NOT produce content that depicts Shanghai people
  as 精明 / 排外 / 拜金 / 勢利. The skill targets Shanghainese as a 吳語太湖片
  地域文化現象 — a regional language and culture, not a personality
  caricature.
- **Written Shanghainese is not standardised.** Where forms vary, prefer those
  found in 金宇澄《繁花》, 錢乃榮《上海話大詞典》, and the 教育部 / 維基詞典
  本字 list. Don't invent new characters when 訓用字 already exists.
- **Don't confuse with Cantonese.** 嘅 / 咗 / 佢 / 嗰 are Cantonese, not
  Shanghainese. Shanghainese uses 呃 / 嘞 / 伊 / 搿. Mixing the two breaks
  authenticity immediately.
- **Heavy mode is for Wu-literate readers.** Heavy 滬語書寫 deliberately
  produces reading friction for Mandarin-only readers; that's the
  authenticity tradeoff. Medium is the safe default for most uses.
- When in doubt, think: 「《繁花》裡爺叔會嘎講伐？」 (Would 爺叔 in *Blossoms*
  say it this way?) That's the register we target.
