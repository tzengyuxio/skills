# Chinglish — 中式英語化

將中文或英文轉換為 Chinglish（中式英語）——帶有中文語法、語序和思維模式痕跡的英文，重現招牌、菜單、說明書和日常對話中常見的「中式英文」風格。

## 功能

依照 25 項 checklist 將文字轉為 Chinglish 風格，涵蓋以下模式：

| 類別 | 項目 |
|------|------|
| **語法模式** (G1-G8) | 冠詞缺失、繫詞省略、主題句式、時態扁平化、主動一致性、複數消失、代名詞混淆、雙標記連接詞 |
| **詞彙模式** (V1-V8) | 開/關萬用、「給」當介詞、「吃」萬用、形容詞當副詞、「很」的過度使用、「有」的存在句式、「玩」萬用、成語直譯 |
| **介詞與語序** (P1-P3) | 時間地點前置、介詞錯配、疑問句不倒裝 |
| **結構模式** (S1-S4) | 冗贅客套語、招牌菜單翻譯體、「請」的過度使用、逗號連綿 |

支援三段強度：

| 強度 | 說明 |
|------|------|
| **輕** | G1-G5（冠詞、繫詞、主題句式、時態、主動一致性），像是有偶爾失誤的進階學習者 |
| **中**（預設） | 輕 + G6-G8, V1-V8, P1-P3, S4，明顯的中式英文——語序錯、成語直譯、逗號連綿 |
| **重** | 全套含 S1-S3，讀起來像招牌/菜單機器翻譯——冗贅客套、辭典亂選、荒誕迷人 |

## 使用方式

```
/chinglish path/to/article.md
```

**觸發詞：** `/chinglish`、「寫成中式英文」、「翻成中式英語」、「Chinglish化」、「make it chinglish」

支援兩種輸入：
- **中文輸入** → 以中式思維直譯為英文
- **英文輸入** → 將標準英文改寫為中式英文

## 運作流程

1. **載入** — 讀取檔案或行內文字
2. **轉換** — 依 checklist 逐項套用 Chinglish 模式
3. **輸出** — 另存為 `_chinglish` 後綴新檔，附 3-5 組前後對比

## 範例

| 原文 | Chinglish |
|------|-----------|
| Turn on the light. | Open the light. |
| Although it rained, we went out. | Although rain, but we still go out. |
| There are many people here. | Here have many people. |
| She sings beautifully. | She sing very beautiful. |
| I studied at the library yesterday. | I yesterday at library study. |
| It's very crowded. | People mountain people sea. |
| Come on! You can do it! | Add oil! |
| Caution: Wet Floor | Carefully Slide *(Heavy)* |

> 完整示範（3 強度 × 2 源文）請見 [examples/demo.md](./examples/demo.md)。

## 背景

Chinglish（中式英語）是中文母語者在使用英文時，因母語語法干擾（L1 transfer）而產生的系統性變異。它不是隨機的「爛英文」，每一個「錯誤」都可追溯至中英文法的結構性差異：

- **冠詞缺失**：中文沒有 a/an/the 的概念
- **繫詞省略**：中文「天氣很好」不需要「是」
- **語序差異**：中文時間、地點在動詞之前
- **動詞不變形**：中文動詞無人稱、時態變化
- **主題優先**：中文是主題導向語言（topic-prominent），英文是主語導向（subject-prominent）

Chinglish 的研究可參考以下來源：

- [Wikipedia: Chinglish](https://en.wikipedia.org/wiki/Chinglish) — 綜合概述與豐富例句
- Joan Pinkham, *The Translator's Guide to Chinglish* (2000) — 系統性分析中式英文的成因與對策
- Oliver Lutz Radtke, *Chinglish: Found in Translation* (2007) — Chinglish 招牌攝影集
- Liu, Wen, et al. "Analysis of Chinglish from the perspective of interlanguage" (2016)

## 相關技能

- [singlish](../singlish/) — 新加坡式英語（同為華語基底的英語變體，但屬克里奧爾語言）
- [westernise](../westernise/) — 為中文加上翻譯腔（逆方向的語言干擾）
- [dewesternise](../dewesternise/) — 去除中文的歐化寫法
- [hanjify](../hanjify/) — 將英文漢字化（不同維度的中英混合）
