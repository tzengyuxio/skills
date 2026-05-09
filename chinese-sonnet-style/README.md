# Chinese Sonnet-style — 改寫成中文十四行詩

把任何現代散文壓縮、淘洗、合律，填入十四行詩的結構——**14 行、每行
10-12 字、4-5 頓、押韻方案合譜、轉折點必現**。主走馮至《十四行集》
(1942) 的沉思凝視基調，結構參照 Petrarchan (義式 8+6) 或 Shakespearean
(英式 4+4+4+2) 兩種。

不是「把段落切成 14 行」、不是「在散文上加韻腳」，而是**先選一個結構，
再依該結構的押韻方案、轉折位置、起承轉合把意義壓進 14 行**。

## 一句話靈魂

**結構合譜、頓挫合度、轉折必現**——三條缺一就不是十四行詩。

## 三條風格指紋

1. **S-01~S-04 結構合譜** — 嚴格 14 行；每行 10-12 字 4-5 頓；押韻方案
   依 Petrarchan / Shakespearean 二擇一；格式標籤必出
2. **M-01 轉折點必現** — Petrarchan 第 9 行;Shakespearean 第 9 行或
   第 13 行;volta 須能感知
3. **C-01 具體意象 ≥4 個** — 物 / 景 / 動作承擔哲思，禁全篇抽象抒情
   詞堆砌 (愁 / 思 / 悲 / 念)

三者缺一就不是十四行詩。其餘 18 條 checklist 都在服務這三條。

## 兩種結構

| 結構 | 行數分配 | 押韻方案 | 轉折點 | 適合題材 |
|---|---|---|---|---|
| **Petrarchan** (義式) | 8+6 | ABBA ABBA CDE CDE (或變體) | 第 9 行 | 沉思凝視、生命感悟、自然意象 (馮至 default) |
| **Shakespearean** (英式) | 4+4+4+2 | ABAB CDCD EFEF GG | 第 9 / 第 13 行 | 論述推進、結句刀、警句總綰 |

詳細格律譜 (押韻方案、轉折點、馮至 / 莎翁實例) 見 [SKILL.md](./SKILL.md)。

## 中文音步：頓的處理

中文無 stress-based meter,西方 iambic pentameter 不可直接套。本 skill
走聞一多 / 卞之琳所宗、馮至所實踐的「頓」原則：

- 每行 **10-12 字** 為主軸 (允許 9 / 13 字 ≤4 行)
- 每行 **4-5 頓** (意義頓 / 語法頓自然分割)
- 押韻採 **同部寬韻** (現代漢語通押),不嚴守原型音節構造，但結構位置
  咬死

## 何時使用

- 想把一篇現代散文壓縮為一首合譜的中文十四行詩
- 想體驗「填十四行」這件事的格律約束 (行數、頓、押韻、轉折)
- 想把日常情緒以馮至《十四行集》的結構重新承載
- 想看 Petrarchan vs Shakespearean 結構在中文裡具體長什麼樣子

## 何時**不**用

- 想寫唐詩近體詩 — 用 `tang-poem-style`
- 想填宋詞詞牌 — 用 `song-ci-style`
- 想寫自由體現代詩 — 本 skill 鎖定格律十四行，不做自由體
- 想寫朱生豪式中譯莎劇腔 (戲劇，非十四行) — 用 `shakespeare-style`

## 預期輸出篇幅

固定 14 行,**約 140-180 字** (依每行 10-12 字計，加標題與標籤約 200 字)。

## 適合的源文

- 抒情散文 (生命感悟、自然觀察、節氣感)
- 沉思札記 (一次經驗的反覆咀嚼)
- 哲思短文 (有對立 / 翻轉 / 推進的張力)
- 觀察文字 (從外景翻向內感)
- 帶警句總綰張力的論述 (適合 Shakespearean)

## 不太適合的源文

- 純敘事故事 (有大量人物對話)
- 純技術文件、新聞報導
- 已經是詩的源文 (改寫意義不大)
- 帶大量現代專名的文 (科技 / 品牌 / 流行詞難以承載)

## 安裝

一行安裝：

```bash
git clone --depth 1 https://github.com/tzengyuxio/skills.git /tmp/tz-skills \
  && mkdir -p ~/.claude/skills \
  && cp -r /tmp/tz-skills/chinese-sonnet-style ~/.claude/skills/ \
  && rm -rf /tmp/tz-skills
```

或透過 plugin marketplace:

```
/plugin marketplace add tzengyuxio/skills
/plugin install chinese-sonnet-style@tzengyuxio-skills
```

手動安裝：

```bash
cp -r chinese-sonnet-style ~/.claude/skills/chinese-sonnet-style
```

## 使用方式

```
/chinese-sonnet-style path/to/article.md
```

也可以直接貼一段文字進來，或剛寫完一份文件後無參數呼叫。

**觸發詞:** `/chinese-sonnet-style`、「改寫成十四行詩」「十四行集」
「馮至體」「Petrarchan」「Shakespearean」「八六結構」「四四四二」
「中文格律新詩」「商籁體」「sonnet」

## 運作流程

1. **讀原文 + 提取核心張力** — 一句話自答：「核心張力 = X;轉折位置 = ?」
2. **決定 Petrarchan 或 Shakespearean** — 預設 Petrarchan
3. **抄韻方案在草稿頂端** — ABBA ABBA CDE CDE 或 ABAB CDCD EFEF GG
4. **提取核心意象** — 自然 / 生物 / 物件 / 時間 / 空間五類擇 ≥4 個
5. **分配前 8 (或前 12) 行鋪陳 + 後 6 (或後 2) 行轉合**
6. **寫初稿** — 逐行對譜，先定韻位字
7. **押韻檢查** — 同部即可，結構位置咬死
8. **字數頓挫檢查** — 10-12 字、4-5 頓
9. **標點清理 + 自檢指令** — 全形標點機械驗證計數歸零
10. **Checklist 自檢** — 21 條 (Hard 17 + Soft 4)
11. **抓最弱行重寫** — 通常是轉折點所在行或末句
12. **輸出** — 寫入 `<原檔名>_sonnet.md`

## 改寫原則 (checklist 摘要)

| 類別 | 編號 | 要點 |
|------|------|------|
| Concrete | C-01~C-04 | 具體意象 ≥4 個、禁抽象抒情堆砌、自然意象 ≥1 個、意象內在呼應 |
| Surface | S-01~S-07 | 嚴格 14 行、每行 10-12 字、每行 4-5 頓、押韻方案合譜、格式標籤必出、段落分隔合譜、全形標點 |
| Voice | V-01~V-05 | 馮至式沉思凝視、末句不直白說教、不模仿任一作家口吻、第一人稱可現、文白比例可調 |
| Meta | M-01~M-05 | 轉折點必現、標題格式、不附評論段、格式標籤+韻方案標注、轉折位置標注 |

完整 21 項 checklist 與 12 步 workflow 見 [SKILL.md](./SKILL.md)。

## 結構選擇邏輯

| 題材氣質 | 選 |
|---|---|
| 沉思凝視、生命感悟 | Petrarchan (馮至 default) |
| 論述推進、結句翻盤 | Shakespearean |
| 八行鋪陳→六行翻深 | Petrarchan |
| 三層次分敘→結句刀 | Shakespearean |

## 示範

完整示範 (三個不同結構:Petrarchan / Shakespearean / Petrarchan 變體)
見 [examples/demo.md](./examples/demo.md)。

## License

PolyForm Noncommercial 1.0.0 — 自由用於個人、教育、研究等非商業用途；
商業使用請另洽授權。詳見專案根目錄 [LICENSE](../LICENSE)。

## Changelog

### v1 — 2026-05-09

- 初版:21 項 checklist (Hard 17 + Soft 4)、12 步 workflow、三條靈魂
  條款、3 則示範
- 兩種結構並列:Petrarchan 8+6 / Shakespearean 4+4+4+2;預設 Petrarchan
- 中文音步走「頓」原則 (4-5 頓 / 行),字數彈性 10-12 字為主
- 押韻寬於原型 (同部即可),但結構位置咬死
- 參照樣本：馮至《十四行集》第一首 / 第十六首 / 第二十二首 + 莎士比亞
  Sonnet 18 中譯
- 標點三件套:S-XX hard rule + Step 9 自檢指令 + Anti-pattern 條目

## 參考資料

### 馮至與中文十四行詩

- 馮至，《十四行集》(1942 桂林明日社首版；後收入《馮至詩選》、《馮至
  全集》) — 中文十四行詩的標竿之作,27 首
- 馮至，〈我和十四行詩的因緣〉— 馮至自述對十四行體的理解
- 王澤龍，〈論馮至的《十四行集》〉— 結構與押韻分析
- 黃偉剛，〈淺析馮至二十七首十四行詩韻律〉— 韻律統計

### 中文新詩格律理論

- 聞一多，《詩的格律》(1926) — 三美主張 (音樂美 / 繪畫美 / 建築美)
- 卞之琳，《雕蟲紀曆》— 自由體與格律體並用，「頓」的節奏理論
- Wikipedia, [十四行詩](https://zh.wikipedia.org/zh-tw/%E5%8D%81%E5%9B%9B%E8%A1%8C%E8%A9%A9)
  / [新月派](https://baike.baidu.com/item/%E6%96%B0%E6%9C%88%E6%B4%BE/1434518)

### 西方原型

- The Poetry Foundation, [Learning the Sonnet](https://www.poetryfoundation.org/articles/70051/learning-the-sonnet)
  — Petrarchan / Shakespearean 結構與 volta 解說
- Academy of American Poets, [Sonnet glossary](https://poets.org/glossary/sonnet)
- 莎士比亞十四行詩中譯：朱生豪、梁實秋、屠岸、梁宗岱、辜正坤等多家
  譯本

### 原作

- 馮至《十四行集》、徐志摩《翡冷翠的一夜》、聞一多《死水》、卞之琳
  《雕蟲紀曆》、莎士比亞 *Sonnets* (1609 公有領域)

## 相關技能

- [tang-poem-style](../tang-poem-style/) — 改寫為唐詩近體
- [song-ci-style](../song-ci-style/) — 填宋詞詞牌
- [shakespeare-style](../shakespeare-style/) — 改寫為朱生豪式中譯莎劇腔
  (戲劇，非十四行詩)
- [yu-guangzhong-style](../yu-guangzhong-style/) — 改寫為余光中式抒情
  散文
- [eileen-chang-style](../eileen-chang-style/) — 改寫為張愛玲式蒼涼散文
- [hemingway-style](../hemingway-style/) — 改寫為海明威體中譯版
