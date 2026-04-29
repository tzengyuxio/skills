# Hanjify — 示範

展示 `hanjify` skill 將英文轉換為漢字化英語的輸出效果。源文來自 [`examples/source-texts/`](../../examples/source-texts/)。

每段轉換產出三個版本：

- **Hanjified** — 純漢字＋羅馬後綴
- **Ruby** — HTML ruby 標注，附英文原文讀音
- **Original** — 原始英文

---

## 範例一：小王子（短句）

源文：[little-prince.md](../../examples/source-texts/little-prince.md)

### Original

> The little prince lived alone on a tiny planet, no bigger than a house. He had three volcanoes to clean, and a rose that he loved very much.

### Hanjified

> The 小 王子 住ed 独 on a 微小 惑星, 無 大er than a 家. 彼 持t 三 火山s to 清, and a 薔薇 that 彼 愛ed 甚 多.

### Ruby

> <ruby>小<rt>little</rt></ruby> <ruby>王子<rt>prince</rt></ruby> <ruby>住ed<rt>lived</rt></ruby> <ruby>独<rt>alone</rt></ruby> on a <ruby>微小<rt>tiny</rt></ruby> <ruby>惑星<rt>planet</rt></ruby>, <ruby>無<rt>no</rt></ruby> <ruby>大er<rt>bigger</rt></ruby> than a <ruby>家<rt>house</rt></ruby>. <ruby>彼<rt>He</rt></ruby> <ruby>持t<rt>had</rt></ruby> <ruby>三<rt>three</rt></ruby> <ruby>火山s<rt>volcanoes</rt></ruby> to <ruby>清<rt>clean</rt></ruby>, and a <ruby>薔薇<rt>rose</rt></ruby> that <ruby>彼<rt>he</rt></ruby> <ruby>愛ed<rt>loved</rt></ruby> <ruby>甚<rt>very</rt></ruby> <ruby>多<rt>much</rt></ruby>.

---

## 範例二：小王子（敘事段）

接續同一源文：

### Original

> Every morning, he would clean his volcanoes and water his rose. One day, he decided to leave his planet to explore the universe.

### Hanjified

> 毎 朝, 彼 願d 清 彼之 火山s and 灌 彼之 薔薇. 一 日, 彼 決ed to 去 彼之 惑星 to 探 the 宇宙.

### Ruby

> <ruby>毎<rt>Every</rt></ruby> <ruby>朝<rt>morning</rt></ruby>, <ruby>彼<rt>he</rt></ruby> <ruby>願d<rt>would</rt></ruby> <ruby>清<rt>clean</rt></ruby> <ruby>彼之<rt>his</rt></ruby> <ruby>火山s<rt>volcanoes</rt></ruby> and <ruby>灌<rt>water</rt></ruby> <ruby>彼之<rt>his</rt></ruby> <ruby>薔薇<rt>rose</rt></ruby>. <ruby>一<rt>One</rt></ruby> <ruby>日<rt>day</rt></ruby>, <ruby>彼<rt>he</rt></ruby> <ruby>決ed<rt>decided</rt></ruby> to <ruby>去<rt>leave</rt></ruby> <ruby>彼之<rt>his</rt></ruby> <ruby>惑星<rt>planet</rt></ruby> to <ruby>探<rt>explore</rt></ruby> the <ruby>宇宙<rt>universe</rt></ruby>.

---

## 範例三：日常對話（簡短）

> Good morning! How are you today? The weather is very nice.

### Hanjified

> 善 朝! 如何 是 汝 今日? The 天気 是 甚 良.

### Ruby

> <ruby>善<rt>Good</rt></ruby> <ruby>朝<rt>morning</rt></ruby>! <ruby>如何<rt>How</rt></ruby> <ruby>是<rt>are</rt></ruby> <ruby>汝<rt>you</rt></ruby> <ruby>今日<rt>today</rt></ruby>? The <ruby>天気<rt>weather</rt></ruby> <ruby>是<rt>is</rt></ruby> <ruby>甚<rt>very</rt></ruby> <ruby>良<rt>nice</rt></ruby>.

---

## 形態學重點

| 類型 | 處理方式 | 例子 |
|---|---|---|
| 屈折變化（保留羅馬字） | `-s` / `-ed` / `-ing` / `-er` / `-est` | `volcanoes → 火山s`、`loved → 愛ed`、`bigger → 大er` |
| 派生變化（轉漢字） | `-er(者)` / `-ly(地)` / `-ful(的)` / `un-(不)` | `teacher → 教者`、`actually → 実地`、`beautiful → 美的` |
| 不轉清單 | `a / an / the / of / in / to / on / at` 保留英文 | `on a → on a` |
| 標點與空格 | 遵循英文慣例，不用中文標點 | `.` `,` `?` 維持半形 |

完整規範見 [SKILL.md](../SKILL.md) 與 [hanjify spec](https://github.com/tzengyuxio/hanjify/blob/main/docs/spec.md)。
