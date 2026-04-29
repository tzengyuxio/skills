# Chinglish — 示範

展示 `chinglish` skill 在不同強度下的輸出效果。源文來自 [`examples/source-texts/`](../../examples/source-texts/)。

支援雙向輸入：中文 → 英文（直譯成中式英語）、英文 → 英文（標準英文改寫為中式英語）。

---

## 範例一：雨天故事（中文源）

源文：[weather-rain.md](../../examples/source-texts/weather-rain.md)

> 昨天下午我在圖書館看書的時候，突然下起了大雨。雖然我沒帶傘，但還是決定走路回家。路上人很多，到處都是撐著傘的行人。我全身都淋濕了，回到家才發現鑰匙忘在辦公室了。鄰居看到我的樣子，笑著說：「你怎麼不叫計程車？」我只好苦笑著回答：「我忘了帶錢包。」

### Light

> Yesterday afternoon, when I was reading book at library, suddenly start to rain heavily. Although I didn't bring umbrella, I still decide to walk home. The road has many people, everywhere is people holding umbrella. My whole body get wet, when arrive home I discover key forget in office. Neighbor see my appearance, laugh and say: "Why you don't call taxi?" I can only bitter smile answer: "I forget bring wallet."

### Medium（預設）

> Yesterday afternoon I at library read book time, suddenly start rain very big. Although I no bring umbrella, but still decide walk road go home. Road on people very many, everywhere all is hold umbrella people. My whole body all wet, go back home then discover key forget at office. Neighbor see my appearance, laugh say: "You why not call taxi?" I only can bitter smile answer: "I forget bring wallet."

### Heavy

> Yesterday afternoon time I at library inside read book, suddenly outside begin fall very big rain. Although I no have bring umbrella, but I still decide use walk road method go back home. Road on the people very very many, everywhere all is hold umbrella walk road people. My whole body all give rain make wet, go back arrive home then only discover key forget put at office. Neighbor see my this kind appearance, laugh face say to me: "Please ask, you for what reason not call one taxi?" I only can use bitter smile to answer him say: "I forget bring money bag."

---

## 範例二：小王子（英文源）

源文：[little-prince.md](../../examples/source-texts/little-prince.md)

> The little prince lived alone on a tiny planet, no bigger than a house. He had three volcanoes to clean, and a rose that he loved very much. Every morning, he would clean his volcanoes and water his rose. One day, he decided to leave his planet to explore the universe. He was sad to say goodbye, but he knew he had to go.

### Light

> The little prince live alone at one tiny planet, not bigger than house. He have three volcanoes and one rose, which he love very much. Every morning he clean his volcanoes and give water to his rose. One day he decide to leave his planet, go explore universe. He very sad to say goodbye, but he know he must go.

### Medium

> Little prince alone live at one tiny planet, not bigger than house. He have three volcano and one rose, he very love. Every morning he clean volcano and give rose water. One day he decide leave his planet, go explore universe. He very sad say goodbye, but he know he must go.

### Heavy

> Little prince one person live at one small small planet on, this planet compare house still small. He have three volcano with one rose flower, very very like. Every day morning he give volcano make clean, give rose flower pour water. Have one day he decide want leave self planet, go outside look look universe. Heart inside very sad want say goodbye, but know must must want go.

---

## 招牌／菜單體（Heavy 專屬）

Heavy 強度可進一步模擬中國街頭招牌、菜單的機器翻譯感：

| 中文原文 | Chinglish (Heavy) | 來源類型 |
|---|---|---|
| 小心地滑 | Carefully Slide | 警示牌誤譯 |
| 民族園 | Racist Park | 公園招牌 |
| 干菜類 | Fuck vegetable category | 超市招牌 |
| 請在一米線外等候 | Please wait outside a noodle | 銀行排隊線 |
| 油炸獅子頭 | Fried lion's head | 餐廳菜單 |
| 加油！你能行的！ | Add oil! You can! | 鼓勵語 |

---

## 強度速查

| 強度 | 啟用範圍 | 典型特徵 | 場景 |
|---|---|---|---|
| **Light** | G1–G5 | 偶爾掉冠詞、繫詞、偶有時態錯 | 受過教育的中文母語者寫的 email |
| **Medium**（預設） | 全套 G + V + P + S4 | 動詞不變形、語序錯、成語直譯、逗號連綿 | 一般 Chinglish 對話 |
| **Heavy** | 全套 + S1–S3 | 冗贅客套、辭典亂選、詞詞對譯 | 招牌、菜單、機器翻譯說明書 |

完整 25 項 checklist 見 [SKILL.md](../SKILL.md)。

## 相關示範

- [singlish demo](../../singlish/examples/demo.md) — 同為華語基底的英語變體，但屬克里奧爾語言（語氣詞 lah/lor、動詞 kena 等）
- [hanjify demo](../../hanjify/examples/demo.md) — 不同維度的中英混合：把英文寫成漢字
