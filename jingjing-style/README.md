# Jingjing-style — 改寫成晶晶體

把任何文章改寫成晶晶體——以中文為基底骨架，於句中嵌入「過於簡單、可被
中文替代且替代後無資訊損失」的英文單字或片語。

不是隨便夾英文，不是 code-switching，而是**「明明可以用中文卻用英文」
的炫耀感口語**——讀完讓人懷疑：這人有沒有用中文想過事情。

## 什麼是晶晶體？

晶晶體是 **2016 年起的台灣媒體名媛口語現象**。起源於該年 11 月某次時尚
雜誌專訪，名媛受訪時大量使用「我覺得很 amazing」「fashion 變成是像一個
life style」這類句法，被民眾戲稱為「晶晶體」並沿用至今。

### 語言學定義

語言學上稱為**語碼轉換（code-switching）**的一種特殊變體。不同於一般
雙語者基於專業詞彙、語境精確性的轉換，晶晶體的特徵是：

- **以中文為骨架**——主謂賓位置、語序、連詞皆為中文
- **嵌入不必要的英文字**——所替換的英文詞「換成中文也完全自然，且資訊
  量等同」
- **單字 / 短片語**形式，不拼成完整英文句
- **炫耀感從『不必要』中產生**——若英文是必要的（專業術語、品牌名），
  就不算晶晶體

### 典型句子

- 「我覺得很 amazing」
- 「fashion 變成是像一個 life style」
- 「我這個 weekend 很 busy，有很多 things 要 do」
- 「天氣很 hot，讓我想吃 ice cream」

`jingjing-style` 鎖定這種「中文為基底 + 不必要英文夾雜」的語體現象。

## 一句話靈魂

**不必要的英文字夾雜**——換成中文資訊不減、語感卻變了；炫耀感從這個
落差裡產生。

## 不會做的事

- 不替換真正需要英文的詞（專業術語、品牌名、人名、地名、無中譯詞）
- 不拼成完整英文句（那是 code-switching，不是晶晶體）
- 不附評論段、不附「我的改寫思路」
- **不模擬特定真人說話**（本 skill 模擬的是語體現象本身,不模擬個人
  軼事或語氣）
- **不附帶嘲諷尾巴**（「呢哈哈」「咧」這種帶嘲弄的詞會破壞自然口語底色）

## 三段強度

`jingjing-style` 提供三段強度設計：

| Level | 密度 | 效果 |
|---|---|---|
| **Light** | 每 4–5 句 1 處 | 偶爾 mix 一個 amazing / nice / so |
| **Medium**（預設）| 每 2–3 句 1 處 | 明顯中英夾雜,PTT 上會被截圖 |
| **Heavy** | 每句 1–2 處 | 2016 原汁原味,幾乎每句都有 |

未指定時預設 **Medium**。

## 白名單與黑名單

### 可換（白名單）

- **形容詞**：amazing、nice、cool、cute、big、hot、busy、tired、happy、
  fancy、chic、casual、vintage、trendy
- **動詞**：check、try、share、enjoy、handle、care、focus、support、
  book、cancel
- **名詞**：fashion、life style、style、vibe、party、weekend、meeting、
  project、idea、problem、feeling
- **副詞 / 連詞 / 語氣詞**：really、actually、so、kind of、well、I mean、
  like、okay、maybe、definitely、totally

### 不可換（黑名單）

- 專業術語（algorithm、API、derivative）——保留英文是必要的
- 品牌名（Starbucks、Hermès）——本來就是英文
- 人名 / 地名（Mary、Tokyo）——專名不算炫耀
- 無中譯或中譯極不通用詞（bug、podcast、meme）——中文圈本就以英文使用
- 縮寫（CEO、CPU、HTTP）——日常技術詞

關鍵判準：**換中文後資訊與語意是否等同**？等同就可換，不等同就保留英文。

## 安裝

一行安裝：

```bash
git clone --depth 1 https://github.com/tzengyuxio/skills.git /tmp/tz-skills \
  && mkdir -p ~/.claude/skills \
  && cp -r /tmp/tz-skills/jingjing-style ~/.claude/skills/ \
  && rm -rf /tmp/tz-skills
```

或透過 plugin marketplace：

```
/plugin marketplace add tzengyuxio/skills
/plugin install jingjing-style@tzengyuxio-skills
```

手動安裝：

```bash
cp -r jingjing-style ~/.claude/skills/jingjing-style
```

## 使用方式

```
/jingjing-style path/to/article.md
```

也可以直接貼一段文字進來，或剛寫完一份文件後無參數呼叫。指定強度：

```
/jingjing-style article.md heavy
```

**觸發詞：** `/jingjing-style`、「改寫成晶晶體」「中英夾雜風格」「台灣
名媛體」「晶晶體化」「rewrite as jingjing」「make it jingjing」

## 運作流程（9 步）

1. **讀源文**
2. **找可替換詞**——掃過全文圈出候選
3. **白名單比對**——確認候選詞夠簡單、可中譯
4. **替換適合詞為英文**——依強度密度
5. **檢查不必要性**——可中譯且不損失資訊?
6. **檢查密度**——是否符合預設強度
7. **檢查語氣**——不過於做作、不嘲諷
8. **標點空格清理**——CJK 全形、英文字內部半形
9. **朗讀**——念起來像不像「明明可以用中文卻用英文」的口語?

## 改寫原則（checklist 摘要）

| 類別 | 編號 | 要點 |
|---|---|---|
| Content | C-01~C-05 | 不必要英文字、不可換需英文詞、密度符合強度、選自白名單、可重複 |
| Structure | S-01~S-05 | 中文骨架、單字嵌入不拼完整句、嵌入位置自然、標點空格、篇幅相當 |
| Voice | V-01~V-05 | 自然不做作、同句不堆三詞、口語底色、可用 is like 等片語、形容詞優先 |
| Meta | M-01~M-05 | 不附評論、不附嘲諷、不模擬特定真人、必經白名單比對、不需炫耀式收尾 |

完整 21 項 checklist 與 9 步 workflow 見 [SKILL.md](./SKILL.md)。

## 靈魂條款（一條）

**C-01 不必要的英文字夾雜**——替換進來的英文字必須是「過於簡單、可被
中文取代且替代後無資訊損失」的字。一旦放寬到專業術語或品牌名，產出就
不再是晶晶體，會失去風格辨識度。

其餘 20 條 checklist 都在服務這一條。

## 示範

完整 Before / After 對照（含 Light / Medium / Heavy 三段強度示範與《差
不多先生傳》改寫）請見 [examples/demo.md](./examples/demo.md)。

## Changelog

### v1 — 2026-05-09

- 初版：21 項 checklist（Hard 9 + Soft 12）、9 步 workflow、一條靈魂條款
- 三段強度（Light / Medium / Heavy）對應不同社交場景
- 白名單核心集（形容詞 / 動詞 / 名詞 / 副詞各層）+ 黑名單（專業 / 品牌 /
  專名 / 縮寫）
- 4 則示範：週末分享（Light）+ 職場感想（Medium）+ 雨天故事（Heavy）+
  差不多先生（Medium）

## 參考資料

- Wikipedia, [晶晶體](https://zh.wikipedia.org/zh-tw/%E6%99%B6%E6%99%B6%E9%AB%94)
  — 起源、定義、典型例句
- EnglishOK 中學英閱誌，[從「晶晶體」看語言表達與國際溝通](https://www.englishok.com.tw/toeic/toeic-issue/crystal_lee_english_speaking)
  — 語碼轉換語言學分析
- 天下雜誌，[37 個職場最常見的「晶晶體」中英夾雜台式英文](https://www.cw.com.tw/article/5128799)
  — 辦公室常見詞彙
- ETtoday，[到底 what 是「晶晶體」？](https://www.ettoday.net/dalemon/post/45801)
  — 流行語沿革
- VoiceTube，[「can 掉這個 meeting」辦公室常見晶晶體](https://tw.blog.voicetube.com/archives/76586/)
  — 動詞層的中英夾雜清單

## 相關技能

- [taiwan-mandarin](../taiwan-mandarin/) — 改寫為台灣國語（同樣是台灣
  社會語言學變體，但取向不同——台灣國語是台語接觸下的庶民口語，晶晶
  體是英語接觸下的名媛口語）
- [westernise](../westernise/) — 加歐化翻譯腔（同樣是「在中文中加入外
  語影響」，但歐化是句法層的西化，晶晶體是詞彙層的英文夾雜）
