---
name: written-hokkien
description: >
  Transform text into written Taiwanese Hokkien （台語 / 閩南語 / 台文） — the
  written representation of 台灣閩南語 using either pure-Hanzi orthography
  (Light, all 漢字 per 教育部 700-字詞 + 訓用字） or 漢羅 mixed script
  (Heavy, 本字漢字 + 台羅羅馬字 for 不可漢字化詞 such as ê / beh / kah).
  Applies a 21-item checklist covering Taiwanese syntax, function words
  （阮 / 咱 / 怹 / 毋 / 莫 / 攏）, core vocabulary （本字 / 訓用字）, and
  orthographic consistency. Useful for creative writing, language education,
  cultural appreciation, and bridging Mandarin into 台語書面化.
  Triggers on "/written-hokkien", "改寫成台語", "改寫成閩南語", "改成台文",
  "寫成漢羅", "translate to taiwanese hokkien", "make it hokkien written",
  "台文書面化", "台語書面化", "漢羅混寫", "台羅", "POJ".
argument-hint: [file-path]
allowed-tools: Read, Write, Edit, Glob
---

# Written Hokkien — 台語 / 閩南語 / 台文書面化

Transform text into written Taiwanese Hokkien （台語 / 閩南語 / 台灣閩南語） — the
written representation of a Sinitic language with around 1700 years of history,
spoken today by tens of millions across Taiwan and Southeast Asia. The result
should read like a 台文 short story, a 漢羅 poem by 陳明仁 or 李勤岸， a
column in 《台文通訊 BONG 報》, or a 教育部 textbook for 本土語言課程 — fluent
in Taiwanese syntax and faithful to one of the two standard orthographies.

This skill covers **two intensities**, distinguished primarily by the
**writing system** rather than by syntactic depth:

- **Light = pure Hanzi （純漢字）** — the entire text in 漢字， drawing on the
  教育部 700-字詞推薦用字 plus 訓用字. Suitable for textbooks, newspapers, and
  general readers who prefer Han characters throughout.
- **Heavy = Han-Roman mixed script （漢羅混寫）** — 本字 stay in 漢字， but
  function words and lexemes that resist standard Hanzi (such as **ê**,
  **beh**, **kah**, **siánn**, **leh**) are written in 台羅 (the 教育部
  臺灣台語羅馬字拼音方案， 2006). This is the preferred form in much
  contemporary 台文文學（賴和、鄭清文、陳明仁《路樹下 ê tó͘-peh-á》, 李勤岸 詩集，胡長松，
  陳雷）.

In both intensities the **syntax must be Taiwanese**, not transliterated
Mandarin. A sentence like 「我有去過日本」 is Taiwan Mandarin, not 台文； the
台文 form is 「我有去過日本 ah」(Heavy) or 「我有去過日本矣」(Light).

## Background — Orthographic history

- **白話字 (POJ, Pe̍h-ōe-jī)** — Romanized 閩南語 introduced by Presbyterian
  missionaries in the 1830s; 巴克禮 (Thomas Barclay) completed the first POJ
  New Testament around 1873 (revised 1916). POJ remained the dominant
  Taiwanese script for church communities for over a century.
- **台羅 (Tâi-lô)** — The 教育部 臺灣閩南語羅馬字拼音方案， promulgated
  2006-10-14, integrating POJ and TLPA conventions. Today 台羅 is the
  standard taught in 本土語言課程 and used in 教育部《臺灣台語常用詞辭典》.
- **教育部推薦用字** — Two waves (2007 / 2008, 2009 revision) totalling 700
  字詞 of recommended Hanzi, classified into 本字 (etymological), 訓用字
  (semantic borrowing), and 新造字（新造）. For Heavy mode, words still
  lacking a settled Hanzi (notably ê, beh, kah, leh, siánn-mih variants) are
  written in 台羅.

## Arguments

- `$0` — (Optional) Path to a markdown or text file. If omitted, find the most
  recent text in conversation context or ask the user.

## Step 1: Load the Text

- If `$0` is provided, read the file.
- Input can be **Mandarin Chinese** (rewrite as 台文）, **English / any
  language** (translate to 台文）, or already 台文 (normalise to chosen
  intensity).

## Step 2: Apply Written Hokkien Patterns

The checklist below is grouped into four categories: **Grammar**,
**Vocabulary**, **Writing System**, and **Meta**. Every rule is tagged with
strength (`Hard` = required, `Soft` = recommended) and minimum intensity
(`Light+` / `Heavy`).

The **soul clause** of this skill: Taiwanese syntax + writing-system
consistency. Sentences must follow Taiwanese grammar (not word-for-word
Mandarin), key function words use 本字（阮 / 咱 / 怹 / 毋 / 莫 / 攏 / 敢）;
Light mode keeps everything in 漢字 (training characters allowed), Heavy mode
mixes 本字 漢字 with 台羅 for words that resist standard Hanzi.

---

### Grammar 語法

#### G1. 人稱代名詞 [Hard, Light+]

| 台語 | 對應華語 | 備註 |
|---|---|---|
| 我（góa） | 我 | 同形 |
| 你（lí） | 你 | 同形；亦寫「汝」 |
| 伊（i） | 他 / 她 | 不分性別 |
| 阮（gún / guán） | 我們（不含對方） | 排除式 we |
| 咱（lán） | 咱們（含對方） | 含括式 we |
| 恁（lín） | 你們 | 本字 |
| 怹（in） | 他們 | 本字 |

台語有「阮 vs 咱」的排除 / 含括區分（exclusive / inclusive we），是中文沒有
的語法範疇。改寫時須依對話對象選用。

#### G2. 否定詞系統 [Hard, Light+]

| 台語 | 對應華語 | 用法 |
|---|---|---|
| 毋（m̄） | 不 | 一般否定 |
| 無（bô） | 沒（有） | 存在 / 完成否定 |
| 莫（mài） | 別 / 不要 | 命令否定 |
| 袂（bē / bōe） | 不會 | 能力 / 未來否定 |
| 未（buē / bē） | 還沒 | 體貌否定 |

> **華語：** 你不要走，他還沒到。
>
> **台文 Light：** 你莫行，伊未到。
>
> **台文 Heavy：** Lí mài kiâⁿ，i bē kàu。

#### G3. 體貌助詞「有」「咧」「矣」 [Hard, Light+]

- **有 + V** ：完成 / 經驗（我有食飯 = I have eaten）
- **咧 + V** 或 **V + 咧**：進行（伊咧讀冊 = he is reading）
- **V + 矣（ah / a）**：句末變化貌（食飯矣 = ate already）

> **華語：** 他在睡覺。
>
> **台文 Light：** 伊咧睏。
>
> **台文 Heavy：** I leh khùn。

#### G4. 動詞「欲（beh）」與「攏」「敢」「會」 [Hard, Light+]

- **欲 / beh** = 想要 / 將要（我欲去食飯）
- **攏（lóng）** = 都
- **敢（kám）** = 是否（句首問詢，不是 dare）；**敢有？**
- **會（ē）** = 可以 / 將（會曉游泳 = can swim）；**袂（bē）** 為其否定

> **華語：** 你會不會游泳？我都會。
>
> **台文 Light：** 你敢會曉游泳？我攏會。
>
> **台文 Heavy：** Lí kám ē-hiáu siû-chúi？Góa lóng ē。

#### G5. 句末助詞 [Hard, Light+]

| 助詞 | 功能 |
|---|---|
| 矣 / ah / a | 變化 / 完成（吃了 / 走了） |
| 啦 / lah | 緩和 / 肯定 |
| 咧 / leh | 強調 / 軟化命令 |
| 喔 / o· | 提醒 |
| neh / 呢 | 親暱 / 撒嬌 |
| oh | 訝異 |
| nih / nō͘ | 確認 |

Light 模式以「矣 / 啦 / 咧 / 喔」漢字書寫；Heavy 模式可寫成「ah / lah / leh
/ o·」羅馬字（一致性原則：同篇不忽然換系統）。

#### G6. 連詞 / 介詞 [Hard, Light+]

| 台語 | 對應華語 |
|---|---|
| 佮（kah） / 及（kap） | 和、跟 |
| 抑是（á-sī） | 或是 |
| 因為 | 因為（同字） |
| 所以 | 所以（同字） |
| 若（nā） | 如果 |
| 連 | 連 |
| 對（tuì） | 對 / 從 |
| 共（kā） | 把 / 替 / 對 |

「共（kā）」是台語極關鍵的功能詞，對應華語的多義「把 / 替 / 對」。
> 我共你講（我跟你說）／ 伊共我騙（他騙我）／ 我共冊讀完（我把書讀完）。

#### G7. 處置式與被動 [Soft, Light+]

- 處置：用 **共 + NP + V**（取代華語「把」）
- 被動：用 **予（hōo） + 施事 + V**（取代華語「被」）

> **華語：** 他被老師罵了。
>
> **台文 Light：** 伊予老師罵矣。
>
> **台文 Heavy：** I hōo lāu-su mē ah。

---

### Vocabulary 詞彙

#### V1. 本字核心集 [Hard, Light+]

教育部 700 字詞中最高頻的功能 / 動作字。皆有官方推薦寫法，務必使用。

| 本字 | 讀音（台羅） | 對應華語 |
|---|---|---|
| 阮 | gún / guán | 我們（排除） |
| 咱 | lán | 咱們（含括） |
| 怹 | in | 他們 |
| 恁 | lín | 你們 |
| 厝 | tshù | 家、房子 |
| 食 | tsia̍h | 吃 |
| 行 | kiâⁿ | 走 |
| 走 | tsáu | 跑 |
| 攏 | lóng | 都 |
| 毋 | m̄ | 不 |
| 莫 | mài | 別 |
| 敢 | kám | 是否 |
| 若 | nā | 如果 |
| 共 | kā | 把 / 對 |
| 予 | hōo | 給 / 被 |
| 揣 | tshuē | 找 |
| 看 | khuàⁿ | 看 |
| 聽 | thiann | 聽 |
| 講 | kóng | 說 |
| 知 | tsai | 知道 |

#### V2. 訓用字（同義漢字、台語讀音） [Hard, Light+]

訓用字使用詞義相同的漢字字形來表現台語音讀，意義相符但讀音為台語。

| 訓用字 | 台羅讀音 | 對應華語 |
|---|---|---|
| 真 | tsin | 很 |
| 大 | tuā | 大 |
| 細 | sè / suè | 小 |
| 好 | hó | 好 |
| 歹 | pháiⁿ | 壞 |
| 老 | lāu | 老 |
| 新 | sin | 新 |
| 緊 | kín | 快 |
| 慢 | bān | 慢 |
| 寒 | kuâⁿ | 冷 |
| 燒 | sio | 熱 |

#### V3. 文化詞 [Hard, Light+]

| 台語 | 讀音 | 對應華語 |
|---|---|---|
| 阿公 | a-kong | 爺爺 |
| 阿媽 | a-má | 奶奶 |
| 查埔 / 查甫 | tsa-poo | 男人 |
| 查某 | tsa-bóo | 女人 |
| 囡仔 | gín-á | 小孩 |
| 姑娘 | koo-niû | 姑娘 |
| 頭家 | thâu-ke | 老闆 |
| 辛勞 | sin-lô | 員工 |
| 煩惱 | huân-ló | 擔心 |
| 趣味 | tshù-bī | 有趣 |
| 拍拚 | phah-piànn | 努力 |
| 食飯 | tsia̍h-pn̄g | 吃飯 |
| 飲茶 | lim-tê | 喝茶 |

#### V4. 高頻台羅詞（Heavy 必用 / Light 須漢字化） [Hard, Heavy]

這些詞缺乏定型漢字或本字仍在爭議；Heavy 模式直接寫台羅，Light 模式須改寫
為近義漢字。

| 台羅 | 意義 | Light 漢字替代 |
|---|---|---|
| ê | 的 / 屬性助詞 | 的 / 之 |
| beh | 想要 / 將要 | 欲 |
| kah | 到（程度） / 跟 | 甲 / 佮 |
| leh | 進行 / 句末 | 咧 |
| siánn / siáⁿ | 什麼 | 啥 / 啥物 |
| lah / la | 啦 | 啦 |
| ah / a | 矣 | 矣 |
| tio̍h | 對 / 著 | 著 |
| lo·h / lōo | 路 | 路（同形） |
| sī | 是 | 是 |
| bē / bōe | 不會 | 袂 |
| hiah-nī | 那麼 | 遐爾 |
| chiah | 才 | 才 |

---

### Writing System 書寫系統

#### W1. Light = 純漢字一致性 [Hard, Light]

- 全篇 100% 漢字（含教育部推薦字 + 訓用字）
- **不出現羅馬字**（除非為人名、地名、產品名等借形專有名詞）
- 句末助詞用「矣 / 啦 / 咧 / 喔 / 呢」漢字
- 對缺乏定型漢字的詞（如 ê / beh / kah），須換用近義漢字（的 / 欲 / 甲）

> 「阿公咧厝裡食飯，阮欲共伊講一聲，伊毋知影。」（純漢字示範）

#### W2. Heavy = 漢羅混寫一致性 [Hard, Heavy]

- 本字（明確的教育部推薦字）保留漢字
- 缺乏定型漢字 / 高頻虛詞用台羅（**ê / beh / kah / leh / siánn / lah /
  ah / tio̍h** 等）
- 同篇內同一詞固定一種寫法，不忽然在 ê 與 的 之間切換
- 台羅標調符號完整保留（á / à / â / ā / a̍h）；不可只寫不標調

> 「阿公 leh 厝裡食飯，阮 beh kā i 講一聲，i m̄ chai-iáⁿ。」（漢羅示範）

#### W3. 台羅標調規範 [Hard, Heavy]

台羅八聲（含輕聲）對應符號：

| 調 | 符號 | 例 |
|---|---|---|
| 1（陰平） | 不標 | tong |
| 2（陰上） | ́ | tóng |
| 3（陰去） | ̀ | tòng |
| 4（陰入） | -h / -p / -t / -k 結尾不標 | tok |
| 5（陽平） | ̂ | tông |
| 7（陽去） | ̄ | tōng |
| 8（陽入） | ̍ | to̍k |
| 0（輕聲） | -- 前綴 | --ah |

#### W4. 羅馬字與漢字之間的空格 [Hard, Heavy]

- 羅馬字段落視同英文：與相鄰漢字間以**半形空格**分隔
- 例：「阮 beh 食」三段以空格分；不寫「阮beh食」
- 台羅內部連字以連字號 -（hyphen），如 chia̍h-pn̄g（食飯）、a-kong（阿公）
- **標點規則**：羅馬字後接全形 CJK 標點（，。：？！）時，**不需要**額外
  半形空格——CJK 標點本身已視覺隔開。例：`Lí kám 知影？`、`阮 beh 走 ah，
  毋通等矣`。羅馬字後若接半形標點（英文文段），才用標準英文空格慣例。

#### W5. 強度一致性 [Hard, Light+]

同一篇文段內**不可混用** Light 與 Heavy 兩種強度。整篇要嘛純漢字、要嘛
漢羅；中途切換會讓讀者錯亂、也讓書寫系統失去信號功能。例外：兩個 demo
並陳的對照（範例三那種「Light 與 Heavy 並陳」）屬於**示範用途**，每段內
仍各自一致。

#### W6. 文白讀的處理 [Soft, Light+]

台語每個漢字常有「文讀」（書面音）與「白讀」（口語音）兩種讀法，例如
「生」可讀 seng（文）或 seⁿ（白）、「人」可讀 jîn（文）或 lâng（白）。
本 skill 為書面化工具，只決定**字怎麼寫**，不規範讀音；但寫作者需自知
所選漢字在台語朗讀時對應的是文讀還是白讀，避免訓用字選擇與口語讀法
脫節（如該寫白讀詞「人 lâng」卻訓用文讀字「民」，會讓口語朗讀變調）。

---

### Meta 元規則

#### M1. 中性化定位 [Hard, Light+]

台語 / 閩南語 / 台灣閩南語並列稱呼，本 skill 將其視為**語言學現象**而非政
治表態。引用教育部規範與學術研究即可，不採政治團體立場，不論「方言 /
獨立語言」之類爭議定位。

#### M2. 文體靈活 [Soft, Light+]

台文可以是散文、詩、對話、新聞、學術論文。皆可改寫，不限文類；只是某些
文類（如學術 / 法律）在台文中尚少見，改寫時請標註。

#### M3. 朗讀檢查 [Hard, Light+]

完成後**用台語默讀一遍**：若一個句子不能用台語自然念出，多半是 Mandarin
syntax 殘留，須改回台語語序。

---

## Step 3: Choose Intensity & Produce Output

| 強度 | 漢字 | 羅馬字 | 適用場景 | 範例 |
|---|---|---|---|---|
| **Light** 純漢字 | 100% | 0% | 教科書、報刊、字幕、一般讀者、政府文書 | 「我欲去食飯，你欲做啥？」 |
| **Heavy** 漢羅 | ~70% | ~30% | 文學作品、詩、學術論文、台文雜誌 | 「我 beh 去食飯，lí beh 做 siáⁿ？」 |

If the user does not specify, default to **Light**（漢字版較廣為一般讀者接受）。
若使用者明示「文學」「漢羅」「詩」「台羅」「台文雜誌」，選 Heavy。

### Input-Specific Handling

**Mandarin → 台文：**
1. 改寫人稱（我們 → 阮 / 咱；他 → 伊）。
2. 換否定詞（不 → 毋；別 → 莫；沒 → 無）。
3. 改連詞 / 介詞（和 → 佮；把 → 共；被 → 予）。
4. 換實詞（吃 → 食；走 → 行；說 → 講）。
5. 套體貌助詞（了 → 矣；在 → 咧）。
6. 依強度決定：Light 全用漢字；Heavy 標出 ê / beh / kah / siánn 等改台羅。
7. 檢查書寫一致性（W1 / W2）。
8. 標點清理（漢字段全形，羅馬字段視同英文）。
9. 用台語默讀一遍。

**English → 台文：**
1. 先翻為自然口語華語。
2. 套用上述 1–9 步。

---

## Step 4: Output

1. **File output:** Save to `_hokkien` suffix（`article.md` →
   `article_hokkien.md`）。如未提供檔案則直接輸出。
2. **顯示 3-5 組對照句**，原文 → 台文。
3. **列出強度與檢核項**：說明選用 Light / Heavy、最常觸發的 Grammar /
   Vocabulary / Writing System 條目。
4. **詞彙表**：列出本篇出現的本字 / 訓用字 / 台羅高頻詞，附華語對應。

---

## Important Notes

- 這是一個**語體轉換工具**，用於創作、教育與文化欣賞。
- 台語 / 閩南語 / 台灣閩南語並列稱呼，本 skill 視之為一個有完整語法與書寫
  傳統的書寫系統，立場為**語言學現象**，不採任何政治論述。
- **句法走台語**是底線。把華語句子的詞替成台語字而句法不動，產生的是
  「台語讀音的華語」，不是台文 — 必須改造詞序與功能詞。
- **書寫系統一致性**比強度激進度更重要。Light 與 Heavy 在同一篇內混用
  （一段純漢字、一段漢羅）會嚴重損害可讀性。
- 教育部 700 字詞推薦字並非鐵律 — 部分本字仍有學術爭議（如「行」vs「走」
  的歷史層次），但對日常書寫足夠穩定。本 skill 以 700 字詞 + 教育部
  《臺灣台語常用詞辭典》為準。
- 台羅與 POJ 高度相似但有微小差異（如 ts/ch、oo/o·）。本 skill 採台羅；如
  使用者要求 POJ，依其指定改寫。
- 若輸入是現代華語小說 / 新聞，產出多半自然；若輸入是古漢語、法律條文或
  高度抽象的學術摘要，請先告知使用者：產出可能讀來生硬，因為這類文體在
  台文寫作傳統中相對少見。
- 寫成 Heavy 時，請務必**完整保留台羅標調符號**（á / à / â / ā / a̍h）。
  剝離標調的「無調台羅」會喪失可讀性。
