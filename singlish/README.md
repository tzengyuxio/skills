# Singlish — 新加坡式英語

將任何文字轉換為 Singlish（新加坡式英語）——一種以英語為基底，融合閩南語、馬來語、粵語、華語和淡米爾語的克里奧爾語言，重現小販中心和咖啡店裡道地的新加坡口語風格。

## 功能

依照 27 項 checklist 將文字轉為 Singlish 風格，涵蓋以下模式：

| 類別 | 項目 |
|------|------|
| **語法模式** (G1-G8) | 主題句式、繫詞省略、冠詞省略、時態可選、複數省略、主語省略、or not/is it 問句、never 作否定過去式 |
| **語氣詞** (D1-D8) | lah（緩和/團結）、lor（無奈）、meh（質疑）、hor（求同）、leh（軟化）、ah（標記主題）、one（強調特質）、wat（提醒/反駁） |
| **詞彙模式** (V1-V8) | got 存在句、can 應答、kena 被動、動詞重疊、already/liao 完成體、借詞分級（核心 8 / 擴展 13）、語義偏移、damn 強化詞 |
| **結構模式** (S1-S3) | like that 句末強調、感嘆詞（wah lau, alamak）、拼寫慣例（dun, dat, oreddy） |

支援三段強度：

| 強度 | 說明 |
|------|------|
| **輕** | G1-G4 + D1-D3，不改拼寫、不用借詞，像受過教育的新加坡人輕鬆聊天 |
| **中**（預設） | 全套 G + D + V（核心借詞），基本拼寫（dun, dat, dis），大多數句子帶語氣詞 |
| **重** | 全套含 S 類，密集語氣詞、擴展借詞、全套方言拼寫，像小販中心對話 |

## 使用方式

```
/singlish path/to/article.md
```

**觸發詞：** `/singlish`、「寫成新加坡英語」、「translate to singlish」、「make it singlish」

支援任何語言輸入，轉為 Singlish 輸出。

## 運作流程

1. **載入** — 讀取檔案或行內文字
2. **轉換** — 依 checklist 逐項套用 Singlish 模式
3. **輸出** — 另存為 `_singlish` 後綴新檔，附 3-5 組前後對比與借詞表

## 範例

| 原文 | Singlish |
|------|----------|
| The weather is very hot today. | Today weather damn hot sia. |
| Do you want this book or not? | You want this book or not? |
| I went to Orchard Road yesterday. | I go Orchard Road yesterday. |
| He was scolded by the teacher. | He kena scold by teacher. |
| There are so many people here! | Here got so many people one! |
| That's not true! | Where got!? |
| Sure, no problem. | Can, can! |
| Think about it briefly. | You go think think a bit lah. |
| Why didn't they come? | How come they never come leh? |
| The food is really good. | The food damn shiok sia. |

> 完整示範（3 強度 × 2 源文）請見 [examples/demo.md](./examples/demo.md)。

## 背景

Singlish（新加坡式英語）是一種以英語為基底的克里奧爾語言（creole language），誕生於新加坡多語環境中英語、閩南語、馬來語、粵語、華語、潮州語、淡米爾語的長期接觸。它不是「不標準的英語」，而是有完整語法系統的獨立語言。

主要語言學特徵：

- **主題導向**（topic-prominent）：句首放主題，再加評論，與華語一致
- **語氣詞系統**：lah, lor, meh, hor, leh 等語氣詞各有精確的語用功能，保留各自的聲調
- **克里奧爾連續體**（creole continuum）：從接近標準英語的 acrolect 到最口語的 basilect，形成一個連續光譜
- **多語借詞**：自然融合閩南語（kiasu, shiok）、馬來語（makan, kena）等詞彙
- **簡化形態學**：冠詞、複數、時態標記皆為可選

參考資料：

- [Wikipedia: Singlish](https://en.wikipedia.org/wiki/Singlish) — 綜合概述與語法分析
- [Singlish vocabulary on Wikipedia](https://en.wikipedia.org/wiki/Singlish_vocabulary) — 詞彙表與例句
- Leimgruber, Jakob R. E., *Singapore English: Structure, Variation, and Usage* (2013)
- Lim, Lisa, *Singapore English: A Grammatical Description* (2004)
- Gwee, Li Sui, *Spiaking Singlish* (2012) — Singlish 詞典與文化指南

## 相關技能

- [chinglish](../chinglish/) — 中式英語（不同地區的華語基底英語變體）
- [westernise](../westernise/) — 為中文加上翻譯腔（逆方向的語言干擾）
- [hanjify](../hanjify/) — 將英文漢字化（不同維度的中英混合）
