---
name: jingjing-style
description: >
  Transform text into 晶晶體 — a Taiwan colloquial register (起源於 2016 年
  媒體名媛口語現象) characterised by a Chinese sentence frame sprinkled with
  unnecessary English single words or short phrases (amazing / busy / fashion /
  life style / nice / really 等),其炫耀感正來自「明明可以用中文卻用英文」。
  Three intensity levels (Light 每 4–5 句 1 處 / Medium 每 2–3 句 1 處 /
  Heavy 每句 1–2 處)。Useful for stylistic experiments, satire of code-switching
  habits, creative writing, and language education.
  Triggers on "/jingjing-style"、「改寫成晶晶體」、「中英夾雜風格」、
  「名媛體」、「台灣名媛體」、「晶晶體化」、「李晶晶式」、"jingjing",
  "rewrite as jingjing", "make it jingjing".
license: PolyForm Noncommercial 1.0.0
argument-hint: "[file-path]"
allowed-tools: Read, Write, Edit, Glob
---

# Jingjing-style — 晶晶體改寫

把任何文章改寫成晶晶體——以中文為基底骨架，於句中嵌入「過於簡單、可被
中文替代且替代後無資訊損失」的英文單字或片語。讀完讓人覺得：說話者明
明可以一句中文講完，卻偏要 mix 一些 English。

晶晶體是 **2016 年起的台灣媒體名媛口語現象**——起源於該年 11 月某次時尚
雜誌專訪，名媛受訪時大量使用「我覺得很 amazing」「fashion 變成是像一個
life style」這類句法，被民眾戲稱為「晶晶體」並沿用至今。本 skill 模擬
的是這個語體現象本身，不針對任何個人。

## 一句話靈魂

**不必要的英文字夾雜**——替換進來的英文字必須是「過於簡單、可被中文取
代且替代後無資訊損失」的字（amazing / busy / happy / nice / big / hot /
really / actually / so / kind of⋯⋯）。**不可替換真正需要英文表達的詞**
（專業術語、品牌名、人名、地名、無中譯詞）。**炫耀感從「明明可以用中文
卻用英文」中產生**——資訊損失等於零，語氣損失卻很大，這就是晶晶體的指紋。

## Arguments

- `$0` —（選填）Markdown 或純文字檔案路徑。若省略，請使用者提供內文，
  或從對話上下文中找最近編輯的檔案。

## Step 1: Load the Text

- 若提供 `$0`，讀取該檔案。
- 若無引數，找對話中最近撰寫或編輯的 Markdown 檔，或請使用者提供文字。
- 輸入可為任何語言。若非中文，先在心中譯為繁體中文（不必輸出），再做
  晶晶體改寫。

## Step 2: Decide Intensity

晶晶體有三段強度。若使用者未指定，**預設 Medium**。

| Level | 密度 | 效果 |
|---|---|---|
| **Light** | 每 4–5 句 1 處英文字夾雜 | 偶爾 mix 一個 amazing / nice / so，像剛從美國旅遊回來的朋友 |
| **Medium**（預設）| 每 2–3 句 1 處 | 明顯的中英夾雜習慣，PTT 上會被截圖那種 |
| **Heavy** | 每句 1–2 處 | 2016 年原汁原味，幾乎每句都有 1–2 個英文字 |

決定強度後在筆記裡標好：「強度 = X，預期密度 = Y」。

## Step 3: Scan for Replaceable Words（白名單比對）

掃過整篇原文，圈出**可替換為英文的詞彙**——條件是「該英文詞夠簡單，國
中程度即懂；中文版本與英文版本資訊量等同；換了不會有人讀不懂」。

### 白名單核心集（可換）

形容詞 / 程度詞：
- amazing（驚奇／厲害／很棒）、nice（不錯／好）、cool（酷）、cute（可愛）
- big（大）、hot（熱／辣）、cold（冷）、happy（開心）、sad（難過）
- busy（忙）、tired（累）、easy（簡單）、hard（難）、boring（無聊）
- fancy（高級）、chic（時髦）、casual（隨性）、vintage（復古）、trendy（流行）

動詞 / 動作：
- check（確認）、try（試）、share（分享）、enjoy（享受）、handle（處理）
- care（在乎）、focus（專注）、support（支持）、book（預訂）、cancel（取消）

名詞 / 概念：
- fashion（時尚）、life style（生活方式）、style（風格）、vibe（氛圍）
- party（派對）、weekend（週末）、meeting（會議）、project（案子）
- background（背景）、idea（點子）、problem（問題）、feeling（感覺）

副詞 / 連詞 / 語氣詞：
- really（真的）、actually（其實）、so（所以／很）、kind of（有點）
- well（嗯）、I mean（我是說）、like（就像）、okay / ok（好）
- maybe（也許）、definitely（一定）、totally（完全）

### 黑名單（**不可換**）

- **真正需要英文的專業術語**：algorithm、API、quantum、derivative、SaaS——
  這些保留英文是因為中譯損失資訊，不屬於晶晶體
- **品牌名 / 商標**：Starbucks、Hermès、iPhone、Tesla——本來就是英文
- **人名 / 地名**：Mary、John、Tokyo、New York——專名不算炫耀
- **無中譯或中譯極不通用的詞**：bug（錯誤?）、debug、podcast、meme——
  中文圈本就常以英文使用
- **縮寫 / 首字母縮略**：CEO、CPU、HTTP——這些屬於日常技術詞

換句話說：**晶晶體的英文字必須是「換成中文也完全一樣自然、且資訊不
減」**。一旦換中文會奇怪／會減損，就不是晶晶體要做的事。

## Step 4: Apply Substitutions

依強度密度，選擇白名單中**自然嵌入**位置，把該詞替換為英文。注意：

- 中文句法骨架不變——主謂賓的位置、語序、連詞都保留中文
- 英文字以**單字 / 短片語**形式嵌入，**不可拼成完整英文句**（拼成完整
  英文句就變成 code-switching，不是晶晶體）
- 多數情況下英文字直接替換中文詞（「我覺得很 amazing」），少數情況補
  入中文連接（「fashion 變成是像一個 life style」）

### 中英對照範例

合格（合靈魂條款）：

| 原句（中文）| 晶晶體 | 通過理由 |
|---|---|---|
| 我覺得很驚奇 | 我覺得很 amazing | amazing 簡單、可中譯（驚奇／厲害）、無資訊損失 |
| 天氣很熱，讓我想吃冰淇淋 | 天氣很 hot，讓我想吃 ice cream | hot / ice cream 皆白名單級簡單詞 |
| 時尚變成是像一個生活方式 | fashion 變成是像一個 life style | 兩處皆白名單級；保留中文骨架 |
| 我這週末很忙 | 我這 weekend 很 busy | weekend / busy 雙白名單，Heavy 強度典型 |
| 真的很可愛耶 | 真的很 cute 耶 | cute 完全可中譯，純粹炫耀 |

不合格（違反靈魂條款）：

- ✗「我去 Starbucks 買咖啡」——Starbucks 是品牌名，不是「不必要的英
  文夾雜」，這只是日常詞彙
- ✗「我寫一個 algorithm」——algorithm 在專業語境保留英文是必要的，不
  屬於晶晶體
- ✗「I went to the meeting and it was so amazing」——拼成完整英文句
  就成了 code-switching；晶晶體必須以中文為骨架
- ✗「她真是個 fashion girl 呢哈哈」——附帶嘲諷句尾（哈哈／呢這種帶嘲
  弄的詞）違反 M-04，破壞晶晶體的「自然炫耀」基底

## Step 5: Self-check Against Checklist

逐條對照下面 21 條 checklist。任一條 [Hard] 違反就回 Step 4 重寫該段。

### Checklist: Content（內容）

| 編號 | 強度 | 規則 |
|---|---|---|
| C-01 | Hard | **不必要的英文字夾雜**——替換進來的英文字必須可被中文取代且替代後無資訊損失 — **靈魂條款** |
| C-02 | Hard | 不可替換真正需要英文的詞（專業術語、品牌、人名、地名、無中譯詞） |
| C-03 | Hard | 英文字密度符合強度要求（Light 每 4–5 句、Medium 每 2–3 句、Heavy 每句 1–2 處） |
| C-04 | Soft | 替換選自白名單核心集（形容詞 / 動詞 / 名詞 / 副詞各層皆可） |
| C-05 | Soft | 同一英文字在篇內可重複（amazing 可出現多次），符合口語自然性 |

### Checklist: Structure（結構）

| 編號 | 強度 | 規則 |
|---|---|---|
| S-01 | Hard | **中文為主句法骨架**——主謂賓的位置、語序、連詞皆為中文 |
| S-02 | Hard | **英文字以單字 / 短片語形式嵌入**，不可拼成完整英文句（避免變成 code-switching） |
| S-03 | Soft | 嵌入位置自然——形容詞位（很 amazing）、副詞位（really 喜歡）、賓語名詞位（一個 life style） |
| S-04 | Soft | 標點清理：中文句中嵌英文字，**英文字前後不加空格**或加半形空格皆可，但全篇一致 |
| S-05 | Soft | 篇幅與原文相當，不大幅增刪 |

### Checklist: Voice（語感）

| 編號 | 強度 | 規則 |
|---|---|---|
| V-01 | Hard | 語氣自然——像名媛口語、不像翻譯腔 |
| V-02 | Hard | 不過於做作——同一句不堆三個以上英文字（即使 Heavy 強度）|
| V-03 | Soft | 口語為主，可帶語助詞（耶／啦／喔／嘛），維持台灣口語底色 |
| V-04 | Soft | 可用「is like / is really」這類口語片語，但仍以中文骨架包覆 |
| V-05 | Soft | 形容詞 / 副詞密度高於名詞（晶晶體最常替換形容詞） |

### Checklist: Meta（後設）

| 編號 | 強度 | 規則 |
|---|---|---|
| M-01 | Hard | 不附評論段、不附作者按、不附「我的改寫思路」 |
| M-02 | Hard | **不附帶嘲諷句子**——不寫「她真是個 fashion girl 呢哈哈」這種帶嘲弄的詞，晶晶體本身要自然不帶評價 |
| M-03 | Hard | **不模擬特定真人說話**——本 skill 模擬的是 2016 年起的語體現象，不模擬特定個人的語氣、人生事件、私人軼事 |
| M-04 | Hard | 替換的英文字必經白名單比對——若懷疑「這個詞換中文會不自然」就不要換 |
| M-05 | Soft | 篇末不需要特別收尾——晶晶體的餘韻來自整體，不需炫耀式結尾 |
| M-06 | Hard | **CJK 字相鄰標點全形零違規**——CJK 字之間的 ASCII 半形 `, ; : ? !` 計數須為 0；英文字內部標點（don't、it's）保留半形不計入；以 Step 6 自檢指令驗證通過才算合格 |

**總計**：22 條（Hard 10 + Soft 12）。

## Step 6: 標點與空格清理

- **全形標點（鐵律）**：CJK 字之間所有標點一律全形。**ASCII 半形 `, ; : ? !` 在 CJK 字之間出現一律是 bug**，必須換成全形 `，；：？！`。對照表：

  | 半形（禁，當夾在 CJK 字之間時） | 全形（用） | Unicode |
  |---|---|---|
  | `,` | `，` | U+FF0C |
  | `;` | `；` | U+FF1B |
  | `:` | `：` | U+FF1A |
  | `?` | `？` | U+FF1F |
  | `!` | `！` | U+FF01 |
  | `(` `)` | `（` `）` | U+FF08 / U+FF09 |

- **例外**：英文字內部標點保留半形（don't、it's、U.S.）；英文字相鄰的 ASCII 標點（如 `Hello, world` 整段英文）視同英文段，不在自檢範圍。**只檢「CJK 字相鄰的 ASCII 半形標點」**
- **破折號**用兩個全形「—」連寫成「——」，不寫成 `--` 也不寫成單個「—」
- **句號**（中文段）用「。」，不用 `.`
- **全形標點與 CJK 之間零空格**
- 英文字與相鄰中文之間：**全篇一致**（要嘛全程加半形空格「我覺得很 amazing」，要嘛全程不加「我覺得很amazing」）。預設加空格，較易閱讀。
- 英文字保持原拼寫大小寫（amazing 小寫；專名 Vogue 首字母大寫）

- **寫完後必跑自檢指令**（指令名留作機械驗證；正則已調整為只檢 CJK 字相鄰的半形標點，英文段內部不誤抓）：

  ```bash
  python3 -c "
  import re, sys
  text = open(sys.argv[1]).read()
  # 只抓 CJK 字相鄰的 ASCII 半形標點；英文字（a-zA-Z）內部的逗號 / 分號 / 冒號 / 問號 / 感嘆號不算違規
  bad = re.findall(r'[一-鿿㐀-䶿][,;:?!][一-鿿㐀-䶿]', text)
  print(f'half-width punct between CJK: {len(bad)}')
  for b in bad[:5]: print(repr(b))
  " 輸出檔.md
  ```

  結果必須為 `0`。非 0 表示輸出時混入了 ASCII 半形於 CJK 字之間，回到輸出檔逐字替換後重跑，直到歸零才算交付。

## Step 7: 朗讀與密度檢查

朗讀全文：

1. 念起來像不像「明明可以用中文卻用英文」的口語？若像翻譯腔（先用英
   文想再翻成中文）就違反 V-01
2. 數英文字密度——是否符合預設強度？太稀就再加一點，太密就刪掉幾個
3. 是否有任何句子拼成完整英文句？若有，違反 S-02，改為單字嵌入

## Step 8: Output

1. **檔案輸入**：寫入 `<原檔名>_jingjing.md`，保留原檔
2. **貼文輸入**：直接輸出晶晶體
3. **不附說明、不附評論、不附「我的改寫思路」**
4. 若使用者明確要求，可額外列出**替換清單**（中文 → 英文逐字對照），
   但**主輸出永遠是晶晶體本身**

---

## 9-step Workflow 速記

1. 讀源文
2. 找可替換詞（圈出）
3. 用白名單比對
4. 替換適合詞為英文
5. 檢查是否「不必要」（可中譯不損失資訊?）
6. 檢查密度（是否符合強度）
7. 檢查語氣自然度（不過於做作、不嘲諷）
8. 標點空格清理
9. 朗讀

---

## Anti-patterns（常見失敗模式）

寫完一稿、自檢之前，先掃一眼這 7 條最容易踩的坑：

1. **替換不必要的詞** — 把 algorithm / blockchain / Starbucks 這種「該
   英文就英文」的詞算進英文字密度，會稀釋掉晶晶體的炫耀感（違反 C-02）
2. **拼成完整英文句** — 寫出「I really love this fashion」這類整句英
   文，就成了 code-switching 而非晶晶體（違反 S-02）
3. **同句堆三個以上英文字** — 「我 really 覺得這個 fashion brand 真的
   很 amazing」這種堆疊讀起來像在炫耀清單，不自然（違反 V-02）
4. **帶嘲諷尾巴** — 替主角加「呢哈哈」「咧」這種帶嘲弄的語氣詞，背離
   晶晶體本身的自然炫耀基底（違反 M-02）
5. **白名單以外的詞硬換** — 把「我寫了一個演算法」改成「我寫了一個
   algorithm」會破壞「無資訊損失」原則。演算法在技術語境保留英文是
   必要的，不是炫耀
6. **翻譯腔** — 先用英文想，再字字翻成中文加幾個英文字。晶晶體的骨架
   必須是「中文先想出來」的中文，再點綴英文。語感不同
7. **半形標點混入 CJK 字之間** — 把中文句子的逗號 / 句號 / 問號等打成 ASCII
   半形而非全形（如「我覺得很amazing,真的」應為「我覺得很 amazing，真的」）。
   英文字內部的標點（don't、it's）不算違規。寫完務必跑 Step 6 自檢指令，
   計數歸零才算交付（違反 M-06）

---

## Important Notes

- 本 skill 是**體裁轉換工具**，模擬的是 **2016 年起的台灣媒體名媛口語
  現象**——不針對任何個人，不模擬特定真人的語氣、軼事、人生事件
- **晶晶體不是錯誤的中文**——它是一個有系統的口語社會語言學現象，與「炫
  耀雙語能力」「身分標記」等社會語意有關。本 skill 視之為中性語體變
  異，不作貶抑
- **替換範圍嚴格限白名單** — 「不必要的英文字」是靈魂條款。一旦放寬
  到專業術語或品牌名，產出就不再是晶晶體，會失去風格辨識度
- **三段強度是傳統設計** — Light / Medium / Heavy 對應不同社交場景，
  使用者未指定時預設 Medium。Heavy 為 2016 年原汁原味
- **語氣不過於做作、不附嘲諷** — 晶晶體本身要寫得自然，由密度與「不必
  要性」自帶炫耀感，**不需要敘述者額外加嘲諷的句子或語氣詞來「強調」
  這是晶晶體**——那會破壞自然口語底色
- 清單並非窮盡一切，使用判斷力標記其他感覺不對的句子
