# Psychoanalytic-lens — 用精神分析的眼光重寫敘事

把一篇文章改寫成「**它自己用精神分析的眼光看自己**」的版本。事件保留,
意義重組。

## 這是一個 lens skill,不是 style skill

本 repo 此前的改寫類 skill(莎劇腔、金庸體、聊齋體、瓊瑤體⋯⋯)都是
**style skill**——改變語言表面:句法、詞彙、節奏、體裁慣例。

`psychoanalytic-lens` 是這個 repo 的**第一個 lens skill**——它不主動改變
表面語言,而是改變**詮釋框架**:同一個事件,被重新敘述為慾望的迂迴、
症狀作為訊息、或大他者凝視之下的演出。

| 維度 | style skill | lens skill(本 skill)|
|---|---|---|
| 改變什麼 | 語言表面(句法 / 詞彙 / 節奏)| 詮釋框架(動機 / 意義 / 心理切片)|
| 事件可動 | 視 skill 而定 | **絕不可動** |
| 失敗模式 | 詞彙堆砌、體裁 caricature | 變成論文式評論貼在原文後 |

## 一句話定位

讓文章的**內部敘述本身**變成精神分析,而不是在文章後面接一篇分析評論。

## 何時使用

- 想看一篇文章被「精神分析的耳朵」聽完之後的樣子
- 想把表面行為(簽約 / 失眠 / 加班 / 沉默)重新組織為它的象徵性根源
- 想用慾望、壓抑、伊底帕斯結構、大他者的凝視⋯⋯這些概念自然嵌入敘事
- 想保留原文事件骨架,但改寫文章對自己的詮釋

## 不適用

- 想要一篇精神分析論文式的評論(本 skill 嚴禁這條路線)
- 想要對作者本人下精神分析診斷
- 想要翻譯精神分析經典文本
- 純技術文件、無人物無動機的說明文字

## 三條核心條款

1. **事件保留** — 不可竄改敘事事實。只能重寫動機句、意義句、心理活動
   句、敘述者插話
2. **概念自然發生** — 概念須從事件自然長出,不可貼標籤式塞入。一篇文
   章 1 個主軸 + 1–2 個副概念為極限
3. **替代敘述義務** — 至少 1 處把表面行為的主敘述替換為象徵性根源
   (是改寫主敘述,不是加註)

## 安裝

```bash
git clone --depth 1 https://github.com/tzengyuxio/skills.git /tmp/tz-skills \
  && mkdir -p ~/.claude/skills \
  && cp -r /tmp/tz-skills/psychoanalytic-lens ~/.claude/skills/ \
  && rm -rf /tmp/tz-skills
```

或手動安裝:

```bash
cp -r psychoanalytic-lens ~/.claude/skills/psychoanalytic-lens
```

## 使用方式

```
/psychoanalytic-lens path/to/article.md
```

也可以直接貼一段文字進來,或剛寫完一份文件後無參數呼叫。

**觸發詞**:`/psychoanalytic-lens`、「精神分析重寫」「用精神分析改寫」
「Freudian rewrite」「Lacanian narrative」「潛意識視角」「拉康式改寫」
「佛洛伊德角度」

## 示範

完整的 3 則改寫示範(《差不多先生傳》/ 雨天故事 / 簽約軼事——各自主走
不同的核心概念)見 [examples/demo.md](./examples/demo.md)。

## License

PolyForm Noncommercial 1.0.0
