---
name: mainland-mandarin
description: >
  Transform text into Mainland China Mandarin （中國大陸普通話） — the everyday
  spoken and media register of the People's Republic of China. Features
  PRC-specific everyday vocabulary （視頻/質量/出租車/公交/軟件/互聯網/視
  頻/屏幕/鼠標）, administrative-life terms （戶口/社保/落戶/北漂/公積金）,
  social-platform terms （微信/朋友圈/微博/熱搜/B站/彈幕/抖音/小紅書/拼多
  多/美團）, and 2020-2025 internet slang （內卷/躺平/yyds/破防/絕絕子/家人
  們誰懂啊/友友們/666/拿捏/鴿了/翻車/emo 了/蚌埠住了/citycity/偷感很重
  /草台班子）. Three intensity levels from light vocabulary swap to heavy
  抖音/B站 caption/弹幕 style. NOT party-state bureaucratese (use
  prc-bureaucratese for that), NOT a sub-dialect (use dongbei-mandarin /
  sichuan-mandarin / shanghainese for those). Useful for creative writing,
  cultural understanding, language education, or humor.
  Triggers on "/mainland-mandarin", "寫成大陸普通話", "改成中國大陸中文",
  "翻成大陸普通話", "中國大陸風格", "簡體字風", "微博體", "抖音體",
  "B 站體", "make it mainland mandarin", "PRC mandarin", "中國風中文",
  "內卷", "躺平", "yyds", "家人們誰懂啊".
license: PolyForm Noncommercial 1.0.0
argument-hint: [file-path]
allowed-tools: Read, Write, Edit, Glob
---

# Mainland Mandarin — 中國大陸普通話

Transform text into Mainland China Mandarin （中國大陸普通話） — the everyday
spoken and media register of the People's Republic of China. The result should
read like a Beijing-based journalist writing for 澎湃新聞， a 微博 user posting
about her morning commute, a 小紅書 lifestyle 種草 caption, an 知乎 answer, or
a 抖音 / B 站 video script — unmistakably 大陸口吻 in 詞彙、句法、平台文體
與網路用語層。

中國大陸普通話 is **not** party-state bureaucratese （人民日報社論的「紮實
推進、深入貫徹」那一套）, and it is **not** a regional sub-dialect （東北、四
川、上海話那種）. It is the **standard everyday register** of mainland speech
and writing — the layer that holds together microblog posts, news stories,
chat messages, comment-section banter, and short-video scripts across the
country.

This skill targets the **written representation** of that register — the
everyday lexicon, sentence rhythm, internet vernacular, and platform-specific
flavor that surface on screen.

## Arguments

- `$0` — (Optional) Path to a markdown or text file. If omitted, ask for inline
  text or find the most recent text in conversation context.

## Step 1: Load the Text

- If `$0` is provided, read the file.
- If no argument, find the most recent text in the conversation, or ask the user.
- The input can be **any Mandarin text** (rewrite as Mainland Mandarin), **any
  language** (translate to Mainland Mandarin), or **English** (translate to
  Mainland Mandarin).

## Step 2: Apply Mainland Mandarin Patterns

Apply the rules below systematically. Goal: every paragraph carries multiple
Mainland Mandarin markers — at least one of {大陸特有日常詞、行政生活詞、
社交平台詞、網路用語} per 2-3 sentences. Not every rule applies to every
sentence — pick what fits.

中國大陸普通話 sits on a continuum from neutral journalistic prose (lightly
PRC-flavored) down to heavy 抖音 / B 站 / 微博 caption style. This skill
covers that full continuum and deliberately excludes both party-state public-
document register (`prc-bureaucratese` covers that) and regional sub-dialects.

---

### Grammar Patterns（語法模式）

#### G1. 「了 / 過」體標記 — 與通用普通話一致 [Hard, Light+]

Aspect markers 了 / 過 work essentially the same as in Standard Mandarin —
this skill does **not** treat aspect as a divergence axis. The Taiwanese
「有」+ V completion pattern (「我有吃飯」) is **avoided** in Mainland
Mandarin and counts as a Taiwan marker; rewrite to standard 了 / 過.

> **Taiwan flavor:** 你有去過北京嗎？
>
> **Mainland:** 你去過北京嗎？

> **Taiwan flavor:** 我有吃飯了。
>
> **Mainland:** 我吃過了。 / 我吃了。

#### G2. 「在」+ V 進行式偏好 [Soft, Medium+]

Mainland Mandarin leans on 「在」+ verb (or 正在 + V) for ongoing action
slightly more than Taiwan, where 「正在」 is more bookish.

> **Standard:** 他寫作業。
>
> **Mainland:** 他在寫作業呢。

> **Standard:** 我看新聞。
>
> **Mainland:** 我正在看新聞。

#### G3. 「給」字句的口語擴張 [Soft, Medium+]

Mainland 口語 uses 「給」 freely for benefactive, dative, and casual
disposition — somewhat more pervasively than Taiwan's textbook usage.

> **Standard:** 我幫你買一個。
>
> **Mainland:** 我給你買一個。

> **Casual:** 你給我整點兒吃的。 *(careful: 整 here drifts toward 東北
> register; in plain Mainland Mandarin use 弄 / 拿 instead)*
>
> **Plain Mainland:** 你給我拿杯水。

#### G4. 「咱 / 咱們」拉近距離 [Soft, Medium+]

Mainland speakers (especially north of the Yangtze, but media-wide too)
use 「咱 / 咱們」 to include the listener — slightly more frequent than
Taiwan's 「我們」default.

> **Standard:** 我們先吃飯。
>
> **Mainland （媒體 / 北方口語）:** 咱先吃飯。

#### G5. 數字單位 — 萬 / 億 為基本單位 [Hard, Light+]

Mainland uses 萬 / 億 as the primary larger units (same as Taiwan; **不同於
新加坡華語的「千」單位**). Numbers between 10,000 and 99,999,999 are
counted in 萬.

> **Mainland:** 三萬五千人 / 5,000 萬粉絲 / 1.2 億用戶
>
> 不寫： 35 千人（那是新加坡華語）

#### G6. 量詞偏好 — 個 / 件 / 條 / 場 [Soft, Light+]

Mainland 口語 leans on 「個」 even where stricter Mandarin grammar would
prefer a specific classifier. Don't overcorrect classifier mismatches that
sound natural in PRC speech.

> 一個項目、一個事兒、一個朋友、一個建議

#### G7. 「了」字句末重音 — 完成感標記 [Soft, Medium+]

Mainland casual ending 「⋯⋯了」 carries a finality / change-of-state
flavor and is freely reduplicated for emphasis: 「我吃了了」「行了行
了」「好了好了」.

> 行了行了，別說了。
>
> 好了好了，知道了。

---

### Vocabulary Patterns（詞彙模式）

#### V1. 大陸特有日常詞彙 — 對台差異核心集 [Hard, Light+]

The most reliable signal of Mainland Mandarin. Swap these freely at all
intensities.

| 大陸 | 台灣 | 備註 |
|---|---|---|
| 視頻 | 影片 | YouTube / B 站 / 抖音 都是「視頻」|
| 質量 | 品質 | 「產品質量」非「產品品質」|
| 出租車（的士）| 計程車 | 「打車」= 叫車 |
| 公交（車）| 公車 | 「公交」二字也單用 |
| 地鐵 | 捷運 | 北上廣深都是「地鐵」|
| 軟件 | 軟體 | software |
| 硬件 | 硬體 | hardware |
| 互聯網（網絡）| 網路 | 「上網」「網絡」都用 |
| 移動（互聯網）| 行動 | 「移動端」= 行動裝置 |
| 信息 | 資訊 | 「信息技術」「短信」 |
| 數據 | 資料 | 「大數據」「數據分析」 |
| 鼠標 | 滑鼠 | mouse |
| 屏幕 | 螢幕 | screen |
| U盤 / 優盤 | 隨身碟 | USB drive |
| 打印（機）| 列印（機）| printer |
| 服務器 | 伺服器 | server |
| 質檢 | 品管 | QA |
| 默認 | 預設 | default |
| 內存 | 記憶體 | RAM |
| 攝像頭 | 視訊鏡頭 / 鏡頭 | webcam |
| 短信 | 簡訊 | SMS |
| 摩托 / 摩托車 | 機車 | motorcycle（大陸「機車」= machine） |
| 自行車 | 腳踏車 | bicycle |
| 地道 | 道地 | authentic（地道是正寫）|
| 早高峰 / 晚高峰 | 上班尖峰 / 下班尖峰 | rush hour |
| 二維碼 | QR Code | 大陸已全面本地化 |
| 公里 | 公里 | 同；「千米」較少口語 |
| 班味 | （無對應） | 2024 流行語：上班的疲憊感 |

#### V2. 行政生活詞 [Hard, Light+]

Mainland-specific institutional vocabulary that anchors the register
geographically.

| 詞 | 含義 |
|---|---|
| 戶口 | 戶籍登記，與居住權、教育權、社保掛鉤 |
| 身份證 | 居民身份證（繁體寫「身分證」也通） |
| 社保 | 社會保險（五險）|
| 公積金 | 住房公積金 |
| 落戶 | 取得當地戶口 |
| 北漂 / 滬漂 / 深漂 | 在京 / 滬 / 深無戶口的外來工作者 |
| 體制內 / 體制外 | 在 / 不在公務員與國企體系內 |
| 編制 | 公辦單位的正式員工名額 |
| 考公 / 考編 | 考公務員 / 考事業單位編制 |
| 雙減 | 教育部 2021 雙減政策（減作業 / 減校外培訓）|
| 擺爛 | 放棄努力、隨它去 |
| 內卷 / 卷 | 過度競爭 |
| 躺平 | 拒絕內卷的生活姿態 |
| 牛馬 | 自嘲為被驅使的勞動者（2024 流行）|
| 打工人 | 自嘲式勞動者稱謂 |

**注意：** 凡涉及政治敏感概念（社會主義核心價值觀、共同富裕等），
**保持中性轉述**，不替源文添加政治色彩，也不嘲弄。詞彙本身可使用，
立場處理交給源文。

#### V3. 社交平台與互聯網生態詞 [Hard, Light+]

Mainland's platform ecosystem is unique — these names don't translate.

| 詞 | 含義 |
|---|---|
| 微信 | WeChat |
| 朋友圈 | WeChat Moments |
| 點贊 | 按讚 |
| 公眾號 | WeChat 公眾號 |
| 微博 | Weibo |
| 熱搜 | 熱門搜尋榜 |
| 大 V | 微博大號 / 意見領袖 |
| 抖音 | Douyin（國內版 TikTok）|
| 小紅書 | Xiaohongshu / Rednote |
| B 站（嗶哩嗶哩）| Bilibili |
| 彈幕 | 飄過螢幕的即時評論 |
| UP 主 | B 站視頻作者 |
| 知乎 | 中文問答平台 |
| 拼多多 | 拼多多電商 |
| 美團 | 美團外賣 / 本地生活 |
| 餓了麼 | 餓了麼外賣 |
| 滴滴 | 滴滴出行（叫車）|
| 支付寶 | Alipay |
| 種草 / 拔草 | 推薦 / 完成購買或失去興趣 |
| 帶貨 | 直播電商導購 |
| 直播間 | live-stream room |
| 私域 / 公域 | private domain / public domain（運營術語）|

#### V4. 網路用語 — 2020-2025 流行語 [Hard, Medium+]

The contemporary internet vernacular. Use intensity-gated.

| 詞 / 短語 | 含義 / 備註 |
|---|---|
| yyds | 永遠的神 (GOAT) |
| 絕絕子 | 太絕了，極致讚美 |
| 破防（了）| 心理防線崩潰、被擊中 |
| 拿捏 | 完全掌握、把握住 |
| 鴿了 / 放鴿子 | 爽約 |
| 翻車 | 出岔子、人設崩塌 |
| 翻牆 | 跨越 GFW（敏感詞，慎用；中性敘事可保留）|
| emo 了 | 情緒低落（emotional 縮寫）|
| 蚌埠住了 | 「繃不住了」諧音，笑到忍不住 |
| 666 | 太厲害了（「溜溜溜」諧音）|
| 笑死 / 笑死我了 | 笑爆 |
| 我哭了 | 太感動 / 太離譜 |
| 內卷 | 見 V2 |
| 躺平 | 見 V2 |
| 整活兒 | 搞事情、玩花樣（注意：可能略帶東北色彩）|
| 家人們（誰懂啊）| 短視頻誇張開場語 |
| 友友們 | 親切稱呼觀眾 / 讀者 |
| 寶子 / 寶寶 | 親密稱呼觀眾 |
| 老鐵 | 主播稱觀眾（直播圈通用，但東北色彩較濃，慎用）|
| city 不 city | 2024 抖音熱梗，洋氣不洋氣 |
| 偷感（很重）| 2024 流行：拘謹、鬼鬼祟祟 |
| 草台班子 | 2024 流行：不專業的臨時組合 / 自嘲社會 |
| 那咋了 | 2024 流行：「那又怎樣」，拒內耗 |
| 班味（很重）| 2024 流行：上班的疲憊感 |
| 包的 / 包 X 的 | 2025 流行：「包好的」式肯定 |
| 鼠鼠我啊 | 自嘲性卑微稱呼 |
| 真的栓 Q | 真的謝謝（thank you 諧音）|
| 蚌埠住了 / 繃不住了 | 笑出來 |
| 純路人 | 與此事無關的圍觀群眾 |
| 退退退 | 驅趕式拒絕 |

**強度配置：**
- Light：每段 0–1 處輕度詞（yyds / 666 / 拿捏 偶見）
- Medium：每段 1–2 處（破防、絕絕子、emo 了、家人們、種草、yyds）
- Heavy：每 2–3 句 1 處 + 抖音 / B 站 / 微博 文體配置

#### V5. 表情符號與顏文字 [Soft, Medium+]

Mainland 微博 / 朋友圈 / B 站 has its own emoticon ecosystem, distinct from
PTT / LINE 顏文字.

| 符號 / 縮寫 | 含義 / 場合 |
|---|---|
| 哈哈哈哈 | 笑（密度比台灣的「XD」更主流）|
| 233 / 2333 | 笑（從貓撲 BBS / B 站來）|
| awsl | 啊我死了（被萌到）|
| nbcs | nobody cares（少見）|
| zqsg | 真情實感 |
| kswl | 嗑死我了（CP 飯用語）|
| xswl | 笑死我了 |
| u1s1 | 有一說一 |
| dbq | 對不起 |
| yysy | 有一說一 |
| 😅 / 😭 / 🤣 | 主流 emoji 用法接近通用 |

Heavy mode may stack 2-3 letter abbreviations per paragraph; Light avoids them.

---

### Structure Patterns（結構模式）

#### S1. 句末助詞 — 大陸偏好 [Hard, Light+]

Mainland casual writing leans on a different particle palette than Taiwan.
Avoid Taiwan's 啦 / 喔 / 齁 / 耶 / 捏 stack — those mark Taiwan register.

| 助詞 | 用法 / 場合 |
|---|---|
| 吧 | 緩和、推測、建議（最高頻：「走吧」「行吧」「好吧」）|
| 嘛 | 解釋、自然推論（「不就是嘛」「這不挺好的嘛」）|
| 呢 | 進行 / 軟化問句（「你幹嘛呢？」「他在哪兒呢？」）|
| 哈 | 確認 / 親切（直播 / 朋友圈：「明天見哈」「行不行哈？」）|
| 哦 | 接話 / 提醒（不是台灣的「喔」；「好哦」「知道了哦」較少用）|
| 咯 | 提示、輕嘆（「沒辦法咯」）|
| 唄 | 順理成章式建議（「行了唄」「就這麼著唄」；偏北方）|
| 啊 | 強化 / 開場（「走啊」「咋了啊」）|

**規則：** 一句一個助詞，不堆疊。**禁用** 啦 / 喔 / 齁 / 耶 / 捏 / 醬 等台
灣標誌。**避免** 唄密集（那會偏東北）。

#### S2. 微博 / 朋友圈體 [Hard, Medium+]

Mainland microblog signature features:
- 長句 + 多個逗號層遞，不怕段落內訊息密集
- #話題標籤# 嵌入文字流（例：「#週末好去處#」）
- @ 提及人名
- 表情包 / emoji 在情緒高峰
- 結尾常用「⋯⋯」表餘韻 / 無奈

**Example:**
> 今天逛了半天小紅書，種草了一家咖啡館，就在朝陽門附近⋯⋯結果到了發現
> 排隊倆小時，當場破防😭 #週末翻車現場# 友友們真的別週六去。

#### S3. 抖音 / 短視頻文案體 [Hard, Heavy]

Short-video caption signatures:
- 短句 + 鉤子（前 3 秒邏輯）
- 「家人們誰懂啊」「友友們」「寶子們」開場
- 數字標題（「3 個 / 5 個 / 7 個你不知道的⋯⋯」）
- 「絕絕子」「yyds」「拿捏了」收束
- 大量 emoji + 標點（！！！）

**Example:**
> 家人們誰懂啊！！這家小館子的麻辣燙真的絕絕子，價格還超便宜，老闆
> 還送鵪鶉蛋，當場破防🥹 yyds 真的拿捏了打工人的胃！

#### S4. B 站彈幕 / 評論體 [Soft, Heavy]

B 站 風格：
- 短句 + 顏文字（233 / awsl / xswl）
- 結尾「（）」當笑點 / 補刀
- 「前方高能」「名場面」「下次一定」「爺青回」等彈幕梗

**Example:**
> awsl 這段配樂直接 yyds，xswl 看到第 35 秒繃不住了（）爺青回真的，up
> 下次一定加更。

#### S5. 知乎答題體 [Soft, Light+]

知乎風格：
- 開場「謝邀」（早期）/「先說結論」/「以下是我的觀點」
- 條列「1. / 2. / 3.」拆論點
- 句中插入「其實」「事實上」「客觀來講」
- 結尾「以上」/「供參考」

知乎體偏理性，與抖音 / B 站的口語高密度不同。Light 模式可用此體。

#### S6. 標點 — 全形為主 [Hard, Light+]

Mainland writing uses 全形標點（，。！？「」 / "" '' 等）, with these
quirks:
- 中國大陸偏好 "" / '' 而非「」（後者是台港習慣）；本 skill 預設**不
  強制轉換引號**，跟隨輸入；明確要求「大陸引號」時才換成 "" ''
- ⋯⋯六個點 / 三個點 都常見
- 破折號「——」雙短橫
- 數字、英文縮寫旁邊保留半形（yyds、B 站、 emo、APP）

---

## Step 3: Produce Mainland Mandarin Output

Apply the checklist to transform the entire text. Aim for natural,
consistent Mainland flavor — not caricature, not party-state register.

### Intensity Levels

Each rule is tagged with its minimum intensity (e.g., `[Hard, Light+]` =
active from Light up; `[Soft, Heavy]` = mainly Heavy).

| Level | Active Rules | Effect |
|---|---|---|
| **Light** | G1, G5-G6, V1 （核心對台差異詞）, V2 （行政生活詞）, V3 （平台名）, S1 （吧 / 呢 / 嘛 為主）, S5 （知乎體）, S6. 無網路流行語密集，無短視頻體。 | 澎湃新聞、經濟觀察報式中性媒體報導；大陸朋友寫的微信長文。詞彙明顯大陸但語感平實。 |
| **Medium** (default) | Light + G2-G4, G7, V4 （網路流行語每段 1-2 處）, V5 (emoji 與字母縮寫偶用）, S1 （完整助詞集）, S2 （微博 / 朋友圈體）. | 微博日常發文、小紅書 caption、知乎輕鬆答題；明顯大陸流行語密度，但仍可讀。 |
| **Heavy** | All rules including dense V4 （流行語每 2-3 句一處）, V5 （字母縮寫常見）, S3 （抖音 / 短視頻文案）, S4 (B 站彈幕）. | 抖音爆款文案、B 站熱門彈幕、微博熱搜標題、家人們誰懂啊體；情緒密集、用語飽和。|

If the user doesn't specify, use **Medium**.

### 簡繁體處理

Mainland 官方標準是簡體字。但本 skill **預設跟隨輸入字符集**——繁體
入、繁體出；簡體入、簡體出。明確要求「大陸地道版本」/「轉成簡體」
時，才轉為簡體輸出。不靜默轉換。

### Input-Specific Handling

**Mandarin input → Mainland Mandarin:**
1. 替換對台差異詞彙（V1）：視頻、質量、出租車、公交、軟件、互聯網、
   信息、數據⋯⋯
2. 移除台灣標誌：去掉「有」+ V 完成式（G1）、台灣語助詞（啦 / 喔 /
   齁 / 耶 / 捏）、擬音字（粉 / 素 / 醬 / 偶）。
3. 加入大陸句末助詞（S1：吧 / 呢 / 嘛 / 哈）。
4. Medium+ 加網路流行語（V4）與微博 / 朋友圈體（S2）。
5. Heavy 加抖音 / B 站 體（S3-S4）與字母縮寫（V5）。

**非中文輸入 → Mainland Mandarin:**
1. 先翻成標準中文。
2. 套用上述 Mainland 轉換管線。

---

## Step 4: Output

1. **File output:** Save with `_mainland` suffix (e.g., `article.md` →
   `article_mainland.md`). If no file was provided, output directly in
   conversation.
2. **Show 3-5 representative sentence pairs** comparing Original and
   Mainland Mandarin.
3. **List applied patterns:** Note which major pattern groups (G/V/S)
   were most active.
4. **Glossary:** List Mainland-specific terms, internet slang, and
   platform names used, with brief paraphrase or 對台對應詞.

---

## Checklist — 21 條

### Grammar
- **G-01** [Hard, Light+] 無台灣「有」+ V 完成式（你有去過嗎 → 你去過嗎）
- **G-02** [Soft, Medium+] 「在 / 正在」+ V 進行式自然出現
- **G-03** [Soft, Medium+] 「給」字句口語擴張使用得當
- **G-04** [Soft, Medium+] 「咱 / 咱們」拉近距離（媒體 / 北方口語色彩）
- **G-05** [Hard, Light+] 數字以萬 / 億為基本單位（不用新加坡的「千」）
- **G-06** [Soft, Light+] 量詞「個」適度泛用，不過度糾正
- **G-07** [Soft, Medium+] 「了 / 了了」式句末完成感

### Vocabulary
- **V-01** [Hard, Light+] 對台差異詞至少 3 處（視頻 / 質量 / 出租車 / 公
  交 / 軟件 / 互聯網 / 信息 / 數據 / 鼠標 / 屏幕 任選）
- **V-02** [Hard, Light+] 行政生活詞題材相符時出現 ≥ 1 處（戶口 / 社保 /
  落戶 / 北漂 / 公積金 / 體制內 / 內卷 / 躺平 / 打工人 / 牛馬）
- **V-03** [Hard, Light+] 社交平台名題材相符時保留原名（微信 / 微博 / 朋
  友圈 / B 站 / 抖音 / 小紅書 / 拼多多 / 美團 / 滴滴 / 支付寶）
- **V-04** [Hard, Medium+] 網路流行語密度配合強度（Medium 每段 1-2 處；
  Heavy 每 2-3 句 1 處）
- **V-05** [Soft, Medium+] emoji / 字母縮寫（yyds / awsl / xswl / 233）
  Heavy 模式中等密度

### Structure
- **S-01** [Hard, Light+] 句末助詞用大陸偏好集（吧 / 呢 / 嘛 / 哈 /
  哦 / 咯 / 唄 / 啊），**禁用** 啦 / 喔 / 齁 / 耶 / 捏
- **S-02** [Hard, Medium+] 微博 / 朋友圈式長句段落 ≥ 1 處（# 話題 # / @
  / emoji / ⋯⋯）
- **S-03** [Hard, Heavy] 抖音 / 短視頻文案體 ≥ 1 處（家人們誰懂啊 / 友
  友們 / 鉤子 / 數字標題 / yyds 收束）
- **S-04** [Soft, Heavy] B 站彈幕 / 評論體偶用（233 / awsl / 爺青回 /
  「（）」補刀）
- **S-05** [Soft, Light+] 知乎體可選用（謝邀 / 先說結論 / 以下是我的觀點）
- **S-06** [Hard, Light+] 全形標點為主，跟隨輸入字符集（簡 / 繁），不靜
  默轉換引號

### Meta / 靈魂條款
- **M-01** [Hard, Light+] CJK 標點全形；blockquote CJK 段落單行不換行；全
  形標點與 CJK 之間零空格；例外只給 code block / frontmatter / URL / 副
  檔名 / 純英文段（yyds / B 站 / emo 等英縮在中文段內保留半形）
- **M-02** [Hard, C-class] **PRC 普通話日常 / 媒體文體**：詞彙以大陸現代
  用法為準（視頻 / 質量 / 出租車 / 公交 / 軟件 / 地鐵）+ 網路用語適度嵌
  入（隨強度變化）+ 句法走標準普通話（不台化、不港化、不文言）。Light
  每段 0-1 處流行語、Medium 1-2 處、Heavy 2-3 句一處 + 平台文體飽和。
- **M-03** [Hard, Light+] **中性化**：不寫「五毛」「小粉紅」「白左」「自
  乾五」「美分」「翻牆狗」之類意識形態詞。政治色彩詞（社會主義核心
  價值觀 / 共同富裕 / 民族復興等）若提及，按源文立場中性轉述，不嘲
  弄、不諷刺、不放大。中國大陸是現代華語的標準變體之一，不是笑話
  素材。
- **M-04** [Hard, Light+] **不是黨政公文體**：避免落實 / 推進 / 紮實
  / 全面落實 / 深入貫徹 / 統籌 / 構建 / 健全 / 譜寫 / 偉大復興 / 新時代
  XX 思想為指導 等公文標誌詞。本 skill 寫的是日常 / 媒體 / 網路，不是
  人民日報社論。
- **M-05** [Hard, Light+] **不是次方言**：避免東北色彩（整 / 賊 / 嘎哈 /
  咋整 / 嗯哪 / 老鐵密集 / 杠杠 / 妥妥）、四川色彩（巴適 / 安逸 / 哈
  兒）、上海色彩（儂 / 阿拉 / 蠻 X 的）。「老鐵」「整」單獨出現可以，
  密集就偏東北。
- **M-06** [Hard, Light+] **不是台灣國語**：禁用啦 / 喔 / 齁 / 醬 / 醬子
  / 降 / 偶 / 粉 / 素 / 注音文（ㄉ / ㄇ / ㄅ）/ 母湯 / 歹勢 / 假掰 / 機
  車 等台灣標誌；台灣的「機車」（難搞）在大陸是「摩托車」字面義。
- **M-07** [Soft, Light+] 標誌詞分布**有節奏**，不要堆到讀來像在背
  詞典；網路用語要鑲嵌進句意，不是貼標籤。

---

## Step 5: 9-step Workflow

1. **讀源文**：通讀全文，標出敘事節點、情緒高峰、對話段、平台特性
   （是新聞、軼事、生活分享、產品介紹？）。
2. **選強度**：使用者指定？無則 Medium。Light 給平實媒體稿、Medium 給
   微博朋友圈、Heavy 給抖音 / B 站 文案。
3. **詞彙替換為大陸用法**：通遍掃描 V1 對台差異詞與 V2 行政生活詞，
   能換則換；保留 V3 平台名原樣。
4. **加網路用語**：依強度配置 V4——Light 0-1 處、Medium 每段 1-2、Heavy
   每 2-3 句 1。優先選擇與題材相符的（不要硬塞）。
5. **調整句末助詞**：S1 替換為大陸偏好集（吧 / 呢 / 嘛 / 哈），刪除任
   何台灣標誌（啦 / 喔 / 齁 / 耶 / 捏）。
6. **檢查不踩到 stereotype 雷區**：對照 M-04（不寫公文）、M-05（不寫
   次方言）、M-06（不寫台灣國語）、M-03（中性，不政治嘲弄）。
7. **依強度加平台文體**：Medium 加 S2 微博體；Heavy 加 S3 抖音體 + S4
   B 站彈幕。Light 可選 S5 知乎體。
8. **標點清理**：對照 M-01 與 S-06——全形標點、blockquote 不換行、半
   形空格只在英文 / 縮寫旁、引號跟隨輸入不靜默轉換。
9. **朗讀檢查節奏**：心中默讀一遍——能不能想像一個微博博主、一個小
   紅書達人、一個 B 站 UP 主這樣寫？卡到的地方退回去調節奏。

---

## Important Notes

- **這是風格轉換工具**，用於創意寫作、文化欣賞、語言教育。
- **中國大陸普通話是現代華語的標準變體之一**——它有自己的詞彙系
  統（對台差異 100+ 詞）、社交平台生態、網路用語層、媒體文體傳
  統。本 skill 把這層「日常 / 媒體 / 網路」的標準層獨立出來呈現。
- **中性化**：M-03 是 Hard rule。不寫意識形態羞辱詞、不嘲弄大陸文
  化、不放大政治對立。涉及政治概念時按源文中性轉述。
- **不是公文體**：M-04 是 Hard rule。落實 / 推進 / 紮實 / 譜寫 / 偉大
  復興 等是 `prc-bureaucratese` 的專場，本 skill 不去蹭。
- **不是次方言**：M-05 是 Hard rule。整 / 賊 / 巴適 / 儂 等是其他 skill
  的專場。
- **不是台灣國語**：M-06 是 Hard rule。啦 / 喔 / 齁 / 醬 / 偶 / 粉 等是
  Taiwan 標誌。
- **網路用語有節奏**：堆到每句一處會像在背年度榜單。Medium 每段 1-2
  處才像真人寫的微博。
- **正式 / 古典文本警告**：法律合約、古典詩詞改寫成微博 / 抖音 體會
  產生喜劇效果而非實用結果。改寫前提醒使用者。
- 拿不準時想：**「這是一個北京 / 上海 / 深圳 30 歲白領在微信、微
  博、小紅書上會打出來的字嗎？」「這是 B 站 一個 100 萬粉 UP 主的
  動態嗎？」「這是澎湃新聞的記者寫稿時的中性語感嗎？」** 三者擇一
  即可，不要混搭。
