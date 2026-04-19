---
name: singapore-mandarin
description: >
  Transform text into Singapore Mandarin (新加坡華語) — the Mandarin variety used in
  Singapore, shaped by Hokkien/Malay/English contact, with its own administrative
  vocabulary (組屋/德士/樂齡/客工/新生水/易通卡), phonological-spoken carryovers
  (幾時/不懂/做工/青菜/頭家/燒), Malay loanwords (甘榜/巴剎/沙爹/atas/bodoh),
  word-order flips (先後置: 吃先), special classifiers (一粒/一間), and distinctive
  numerical conventions (99 千 = 99,000). Three intensity levels from formal
  Lianhe Zaobao register down to heavy code-mixed social-media 華語.
  Distinct from Singlish (English-based creole) — this skill's output keeps a
  Mandarin grammatical backbone.
  Useful for creative writing, cultural appreciation, language education, or humor.
  Triggers on "/singapore-mandarin", "寫成新加坡華語", "新加坡華語化", "翻成新加坡華語",
  "translate to singapore mandarin", "make it singapore mandarin", "新加坡中文",
  "SG 華語", "Huayu".
argument-hint: [file-path]
allowed-tools: Read, Write, Edit, Glob
---

# Singapore Mandarin — 新加坡華語

Transform text into Singapore Mandarin (新加坡華語, Huayu) — the Mandarin variety used
in Singapore, shaped by prolonged contact with Hokkien (the majority dialect substrate),
Malay (the national language), and English (the lingua franca of administration).
The result should read like a Singaporean writing on *Lianhe Zaobao*, a blog post on
*Redants*, or a WhatsApp chat with a fellow SG friend — unmistakably Huayu, not
Putonghua, not Taiwan Guoyu.

Singapore Mandarin is **NOT Singlish**. Singlish is an English-based creole; Singapore
Mandarin is Mandarin with a Singaporean flavor. At every intensity level this skill
preserves Mandarin grammatical structure (我/你/他、是/不/的/了) — content words may
code-mix with English/Hokkien/Malay, but the backbone stays Mandarin. If you want
English with Chinese/Malay influence, use the `singlish` skill instead.

This skill targets the **written representation** of SG Mandarin. Simplified characters
are the official standard in Singapore, but this skill **follows the input's character
set** (simplified or traditional) unless you ask otherwise.

## Arguments

- `$0` — (Optional) Path to a markdown or text file. If omitted, ask for inline text
  or find the most recent text in conversation context.

## Step 1: Load the Text

- If `$0` is provided, read the file.
- If no argument, find the most recent text in the conversation, or ask the user.
- The input can be **Mandarin Chinese** (rewrite as SG Mandarin), **any language**
  (translate to SG Mandarin), or **English** (translate to SG Mandarin).

## Step 2: Apply Singapore Mandarin Patterns

Apply the rules below systematically. Goal: every 2-3 sentences should carry at least
one SG marker — a SG-specific term, a Hokkien borrowing, an English code-mix, a
Malay loanword, or a SG-characteristic structure. Not every rule applies to every
sentence — pick what fits naturally.

SG Mandarin exists on a continuum from formal Lianhe Zaobao-style journalistic prose
down to heavy code-mixed casual chat. This skill targets that full range, deliberately
staying on the Mandarin-backbone side of the SG Mandarin / Singlish divide.

---

### Grammar Patterns（語法模式）

#### G1. 先後置 — 時間副詞後置 [Hard, Medium+]

Under Cantonese (and Hokkien) influence, adverbs like 先 move to post-verbal position.
One of SG Mandarin's most recognizable syntactic features.

> **Standard:** 你先走。
>
> **SG:** 你走先。

> **Standard:** 我先吃。
>
> **SG:** 我吃先。

> **Standard:** 讓他先看。
>
> **SG:** 讓他看先。

#### G2. 「字」= 5 分鐘 — 時間單位 [Soft, Medium+]

SG uses 字 (zì) as a 5-minute unit (from Hokkien). "一個字" = 5 minutes; "九個字" = 45
minutes. Appears in casual speech and writing; absent in formal Zaobao prose.

> **Standard:** 七點四十五分。
>
> **SG:** 七點九個字。

> **Standard:** 再等十分鐘。
>
> **SG:** 再等兩個字。

#### G3. 「拜」= 星期 — 日期說法 [Soft, Medium+]

"拜" replaces "星期" (from Hokkien). Common in speech and informal writing; formal
writing still uses 星期 / 週.

> **Standard:** 星期一我去看醫生。
>
> **SG:** 拜一我去看醫生。

#### G4. 「千」作為數字單位 [Hard, Light+]

This is a **structural** feature: SG Mandarin keeps counting in 千 (thousand) up to the
millions, rather than switching to 萬 (ten-thousand) at 10,000 like Taiwan/Mainland.

> **Standard (TW/CN):** 九萬九千人 / 99,000 人
>
> **SG:** 九十九千人 / 99 千人

> **Standard:** 三百五十萬
>
> **SG:** 三千五百千（colloquial） / 3.5 million (often code-mixed)

Even formal Zaobao writing often reads "XX 千" instead of 萬. Apply freely at all
intensities for numbers between 10,000 and 999,999.

#### G5. 動詞重疊 + 一下 — 冗疊結構 [Soft, Medium+]

Verb reduplication plus 一下 (borrowed from Malay/Indonesian reduplication patterns);
standard Mandarin uses one or the other, not both.

> **Standard:** 讓我想一下。 / 讓我想想。
>
> **SG:** 讓我想想一下。

> **Standard:** 你試試。 / 你試一下。
>
> **SG:** 你試試一下。

#### G6. 「有」+ 動詞 — 完成/經驗體 [Hard, Medium+]

Identical to Taiwan Mandarin G1 (same Hokkien substrate). 有 + V replaces 了/過
in casual registers.

> **Standard:** 我去過日本。
>
> **SG:** 我有去過日本。

> **Standard:** 你吃了嗎？
>
> **SG:** 你有吃嗎？

---

### Particle Patterns（語尾助詞）

SG Mandarin has a smaller particle set than Taiwan Mandarin but with distinctive
cross-borrowing from Singlish in Heavy mode.

#### P1. 啦 — 緩和 / 肯定 [Hard, Medium+]

From Hokkien. Softens statements, builds rapport, signals certainty. Very common in
casual SG Mandarin.

> **Softening:** 好啦好啦。
>
> **Certainty:** 就是這樣啦。
>
> **Encouragement:** 試試看啦。

#### P2. 咯 / 囉 — 接受 / 無奈 [Hard, Medium+]

From Cantonese/Hokkien. Conveys resignation, obviousness, or casual acceptance.

> **Acceptance:** 好咯，就這樣吧。
>
> **Obvious inference:** 沒辦法咯。
>
> **Resigned:** 我也沒辦法咯。

#### P3. 嘛 / 罷了 / 而已 — SG 偏好 [Soft, Medium+]

SG prefers **而已** (éryǐ) over Mainland **罷了** (bàle) for "only / just." 嘛 is
used for assertion/obviousness (common across Mandarin varieties).

> **Standard (CN):** 我只是開玩笑罷了。
>
> **SG:** 我只是開玩笑而已。

> **Obvious:** 你知道的嘛。

#### P4. 咧 / leh — 輕柔強調 [Soft, Heavy]

Borrowed from Singlish usage patterns (which itself derives from Hokkien). Adds soft
emphasis, mild protest, or probing tone. In Heavy mode may appear as English-spelled
"leh" rather than 咧.

> **Mild complaint:** 很貴 leh。 / 很貴咧。
>
> **Probing:** 這樣也可以 leh？

#### P5. lah / lor / mah — Singlish 跨界 [Soft, Heavy]

In Heavy-register SG Mandarin, particles from Singlish cross over. These often appear
in Latin script within Chinese text as a code-mixing feature, not as standard Chinese
particles. Use sparingly — 1-2 per paragraph at most; over-stacking crosses into
Singlish territory.

> **Casual:** 我今天不去 lah。
>
> **Acceptance:** OK lor。
>
> **Rhetorical:** 真的 mah？

---

### Vocabulary Patterns（詞彙模式）

#### V1. SG 特有詞彙 — 行政與生活核心集 [Hard, Light+]

The most recognizable signature of SG Mandarin. Swap these freely at all intensities.

| SG | 現代漢語（大陸）| 台灣 |
|---|---|---|
| 德士 | 出租車 | 計程車 |
| 巴士 | 公交車 | 公車 |
| 組屋 | 公房/保障房 | 國宅 |
| 腳車 | 自行車 | 腳踏車 |
| 巴剎 | 菜市場 | 傳統市場 |
| 小販中心 | 美食廣場 | 夜市/小吃街 |
| 樂齡人士 | 老年人 | 長者 |
| 客工 | 外籍勞工 | 外勞 |
| 建國一代 | (無對應) | 開國世代 |
| 擁車證 (COE) | (無對應) | (無對應) |
| 保健儲蓄 | 醫保 | 健保 |
| 新生水 (NEWater) | 再生水 | 再生水 |
| 易通卡 (EZ-Link) | 交通卡 | 悠遊卡 |
| 大牌 | 樓棟號 | 棟號 |
| 快熟面 | 方便面/泡面 | 泡麵 |
| 手提電話 | 手機 | 行動電話 |
| 複印 | 複印 | 影印 |
| 飲管 | 吸管 | 吸管 |
| 花紅 | 年終獎 | 年終獎金 |
| 紅毛 | 老外/洋人 | 外國人 |
| 溼巴剎 | 菜市場 | 傳統市場 |
| 垃圾蟲 | 亂丟垃圾的人 | 亂丟垃圾者 |

#### V2. 閩南語借詞 — 核心集 [Hard, Medium+]

SG's Mandarin absorbs heavily from Hokkien. These appear routinely in blog posts,
informal writing, and dialogue.

| 借詞 | 意思 | 備註 |
|---|---|---|
| 幾時 | 什麼時候 | jǐshí, 很常用 |
| 不懂 | 不知道 | 標誌性 SG 用法 |
| 做工 | 上班 | 不是「幹體力活」 |
| 放工 | 下班 | |
| 怕輸 | kiasu，怕吃虧 | 最有名的 SG 概念詞 |
| 頭家 | 老闆 | thâu-ke |
| 青菜 | 隨便 | chhìn-chhài, 不是「蔬菜」|
| 青色 | 綠色 | 閩南語「青」涵括綠 |
| 好料 | 好吃的東西 / 好東西 | |
| 有料 | 有本事 | |
| 燒 | 燙 / 熱 | sio, 注意：不是「燒」的動作 |
| 吃風 | 度假、旅行 | chia̍h-hong |
| 還錢 | 付錢 / 繳費 | ⚠ 和「歸還」不同 |
| 做莫 | 為什麼 | tsò-mih |
| 敢敢 | 勇敢、大膽 | kánn-kánn |
| 三八 | 多嘴、八卦 | sam-pat |
| 烏魯 | 偏僻 | oo-lu |
| 新客 | 新移民 | sin-kheh |
| 阿兵哥 | 當兵的人 | |
| 阿公 / 阿嬤 | 祖父 / 祖母 | |

#### V3. 馬來語借詞 — 日常與文化 [Hard, Medium+]

Malay loanwords are culturally indispensable; use with respect to their origins.

| 借詞 | 意思 | 原文 |
|---|---|---|
| 甘榜 | 村莊 | kampung |
| 巴剎 | 菜市場 | pasar |
| 沙爹 | 烤肉串 | satay |
| 叻沙 | 咖哩麵 | laksa |
| 榴槤 | 榴槤果 | durian |
| 羅惹 | 羅惹沙拉 | rojak |
| 娘惹 | 土生華人女性 | nonya |
| 峇峇 | 土生華人男性 | baba |
| 沙龍 | 圍裙式服裝 | sarong |
| 惹蘭 | 街道（多用於路名） | jalan |
| 巴迪克 | 蠟染布 | batik |
| atas | 高尚、勢利 | 馬來詞，常用原字母 |
| bodoh | 笨、無知 | 馬來詞，常用原字母 |

#### V4. SG 英語音譯與字母詞 [Hard, Light+]

SG has distinctive English transliterations, and an unusually high density of
alphabet-words (initialisms kept in Latin script).

**音譯**：
| SG | 英文原 | 對照 |
|---|---|---|
| 羅里 | lorry | 大陸「卡車/貨車」 |
| 咕打 | quota | 大陸「配額」 |
| 巴仙 | percent | 大陸「百分比/成」 |
| 杯葛 | boycott | 同 HK，大陸「抵制」|
| 三文治 | sandwich | 同 HK，台灣「三明治」|

**字母詞**（書面常保留拉丁字母，不另作漢譯）：
MRT（地鐵）、HDB（組屋局）、CPF（公積金）、ERP（電子道路收費）、COE（擁車證）、NEWater（新生水，括號中也常寫原文）。

#### V5. 粵語 / HK 共用借詞 [Soft, Medium+]

A smaller layer from Cantonese contact.

| 借詞 | 意思 |
|---|---|
| 大耳窿 | 高利貸 |
| 搭客 | 乘客 |
| 擺烏龍 | 鬧笑話、搞錯 |
| 花紅 | 年終獎（亦見 HK）|
| 拍拖 | 談戀愛 |

#### V6. SG 獨特表達 / 咖啡店隱語 [Soft, Heavy]

Very informal, localized usages — suitable for Heavy mode as authentic flavor, but
signal strong vernacular register.

| 表達 | 意思 | 由來 |
|---|---|---|
| 踢球 | Milo（美祿飲料） | 罐上畫有踢球者 |
| 釣魚 | 茶包泡茶 | 茶包上下浮動 |
| 水草 | 吸管 | 外形相似 |
| 玩臭 | 狡猾、搞小動作 | |
| 沒有劃 | 不划算 | |
| 臭雞蛋 / 雞蛋啊 | 驚嘆詞 | |
| 游乾泳 | 搓麻將 | 洗牌動作 |
| Auntie | 泛稱女性長輩 | 不分親疏 |
| Uncle | 泛稱男性長輩 | 同上 |
| 酒客司機 | 代駕服務 | 1996 年 Comfort Delgro 服務 |

#### V7. 文雅偏好 — 詞彙選擇的人文取向 [Hard, Light+]

A genuine pragmatic feature: SG institutional Mandarin **prefers the more dignified
option** when a neutral and a derogatory-leaning term both exist. Apply in Light and
Medium formal writing.

| 採用（SG 偏好）| 避免（較貶或較冷漠）|
|---|---|
| 樂齡（人士）| 老齡、老年 |
| 客工 | 外勞 |
| 建國一代 | 開國世代 |
| 視障人士 | 盲人 |
| 聽障人士 | 聾啞 |

This is not just vocabulary preference — it's a mild sociolinguistic signal of SG's
multiethnic, official-discourse register. Light-Medium output should reflect it.

---

### Structure Patterns（結構模式）

#### S1. 中英 Code-Mixing [Hard, Medium+]

Insert English words for nouns (office, meeting, project, wallet, key), verbs
(check, send, book), adjectives (OK, fine), and intensifiers (very, super). Keep
English in Latin script.

| 場景 | SG 句 |
|---|---|
| 辦公 | 我要去 office 開 meeting。|
| 數量 | 這個 very 好吃。/ 那個 super 貴。|
| 動作 | Send 一個 email 給我。/ Check 一下 price 怎樣。|
| 日常 | 我的 key 忘在 office 了。|
| 評價 | 那個 place 很 OK 而已。|

**Intensity guidance:**
- Light: 1-2 English words per paragraph (mostly workplace nouns like office, email)
- Medium: 3-5 per paragraph (add common verbs like send/check/book and adjectives like OK/very)
- Heavy: pervasive — every 2-3 sentences has an English insertion

#### S2. 中閩 Code-Mixing — 閩南語短句插入 [Soft, Heavy]

In Heavy mode, whole Hokkien phrases may appear as spice, not just loanwords.

> **Example:** 他做人 ho seh lang（好說話）, 你找他 OK 的。
>
> **Example:** 太貴 lah, 我 boh chhai i（不理他）就走了。

Use sparingly — these phrases are authentic in very casual Heavy Huayu but
shouldn't dominate.

#### S3. Singlish 跨界粒子 [Soft, Heavy]

See P5. Heavy mode can include lah/lor/leh/mah/hor as sentence-final particles.
Treat as code-mixing, not as Mandarin grammar.

#### S4. 字母詞保留拉丁字母 [Hard, Light+]

Unlike Mainland (which localizes HDB as 组屋) or Taiwan, SG writers routinely keep
both forms side-by-side: "我住 Jurong 的 HDB 組屋", "坐 MRT 去". Don't force-translate
MRT / HDB / CPF / ERP / COE into pure Chinese at any intensity.

#### S5. 千-單位數字 [Hard, Light+]

See G4. This is a structural feature active at all intensities.

---

## Step 3: Produce Singapore Mandarin Output

Apply the checklist to transform the text. Maintain Mandarin grammatical backbone
at every intensity — content may code-mix heavily, but subjects/objects/function
words stay Mandarin. If the output starts reading as "English with Chinese nouns,"
pull back toward Mandarin structure — that's drifting into Singlish territory.

### Intensity Levels

Each rule is tagged with its minimum intensity (e.g., `[Hard, Medium+]` = active
from Medium up; `[Soft, Heavy]` = mainly Heavy).

| Level | Active Rules | Effect |
|---|---|---|
| **Light** | G4 (千 單位), V1 (SG 行政詞), V4 (字母詞 + 音譯), V7 (文雅偏好), S1 (1-2 英文詞/段), S4 (字母詞), S5. No Hokkien loanwords (except names), no code-mix particles. | 《聯合早報》正式報導、政府文告級別。 |
| **Medium** (default) | Light + G1-G3, G5-G6 (全語法), V2 (閩南語借詞核心), V3 (馬來語借詞), V5 (粵語借詞), P1-P3, S1 (3-5 英文詞/段). | 部落格、紅螞蟻式半正式，明顯 SG 味。|
| **Heavy** | All rules including V6 (咖啡店隱語), P4-P5 (leh/lah/lor), S2 (閩南語短句), S1 (密集 code-mix). | 社交媒體、WhatsApp 聊天、口語轉寫；仍保留 Mandarin backbone，不倒向 Singlish。|

If the user doesn't specify, use **Medium**.

### Simplified vs Traditional

SG's official standard is simplified Chinese. However this skill **follows the input's
character set by default** — 繁體 in, 繁體 out; 簡體 in, 簡體 out. If the user explicitly
asks for simplified (or for authenticity to SG conventions), then convert to simplified
during output. Don't change the character set unprompted.

### Input-Specific Handling

**Mandarin input → SG Mandarin:**
1. Swap SG-specific terms (V1, V4).
2. Apply 千 number convention (G4) and 文雅偏好 (V7).
3. Insert English code-mixing per intensity (S1).
4. At Medium+, add Hokkien/Malay loanwords where natural (V2, V3) and apply G1-G6
   syntactic features where fitting.
5. At Heavy, add SG-specific colloquialisms (V6) and Singlish crossover particles (P5).

**Non-Chinese input → SG Mandarin:**
1. Translate to Standard Written Chinese first.
2. Apply SG Mandarin transforms as above.

---

## Step 4: Output

1. **File output:** Save to `_singapore` suffix (e.g., `article.md` →
   `article_singapore.md`). If no file was provided, output directly in conversation.
2. **Show 3-5 representative sentence pairs** comparing Original and SG Mandarin.
3. **List applied patterns:** Note which major pattern groups (G/P/V/S) were most active.
4. **Glossary:** List SG-specific terms, Hokkien/Malay loanwords, and transliterations
   used, with Mandarin/English equivalents.

---

## Important Notes

- This is a **stylistic transformation tool** for creative, educational, and cultural
  purposes.
- Singapore Mandarin is a **legitimate Mandarin variety** — the everyday language of
  Singapore's Chinese community, documented in 汪惠迪《時代新加坡特有詞語詞典》(1999,
  1560 entries) and the official 新加坡華語資料庫 (Singaporean Mandarin Database, 2019–).
- **Don't confuse with Singlish.** Singlish is English-based creole (see `singlish`
  skill); SG Mandarin is Mandarin-based. Both exist in SG, both are valid, but they
  have different grammatical backbones. If the output drifts into English grammar
  with Chinese nouns, pull back — that's Singlish, not SG Mandarin.
- **Preserve Mandarin function words.** 我/你/他、是/不/沒、的/了、這/那 stay Chinese
  at every intensity. Code-mixing replaces content words, not the grammatical skeleton.
- **文雅偏好 is real.** SG institutional Mandarin systematically prefers dignified
  terms (樂齡/客工/建國一代) over neutral alternatives. Apply this at Light/Medium for
  formal tone.
- **千-單位 is a structural feature.** Numbers between 10,000 and 999,999 are
  counted in 千, not 萬. Apply even in Light mode.
- **Character set follows input** unless user specifies. Don't silently convert
  between traditional and simplified.
- **Avoid caricature.** The goal is authentic SG Mandarin — the style a Singaporean
  journalist, blogger, or friend would write — not exaggerated stereotypes.
- When in doubt, think: "Would this appear in 聯合早報 (formal), 紅螞蟻 (blog), or
  a WhatsApp group chat among Singaporean friends (casual)?" That's the register
  we target.
