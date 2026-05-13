# 中文古典體式 / Classical Chinese Forms

把文章壓縮、轉譯為**特定時代的中文書面語**，含古文時代體與古典詩詞格律。
**鎖死的是「時代 + 格律」雙重 lock**——字數、句長、押韻、平仄、對仗等形式
規範完全嚴守。

## 收錄 skill（8 件）

### 文言時代體（4 件）

| skill | 一句話功能 | 強度 | demo |
|---|---|---|---|
| [wenyan-xianqin](../wenyan-xianqin/) | 先秦諸子體（《論語》《莊子》《韓非子》風格） | — | [demo](../wenyan-xianqin/examples/demo.md) |
| [wenyan-hanwei](../wenyan-hanwei/) | 漢魏史傳體（司馬遷、班固、陳壽風格） | — | [demo](../wenyan-hanwei/examples/demo.md) |
| [wenyan-guwen](../wenyan-guwen/) | 唐宋古文體（韓愈、蘇軾、歐陽修風格） | — | [demo](../wenyan-guwen/examples/demo.md) |
| [wenyan-huaben](../wenyan-huaben/) | 話本小說體（《水滸》《三國》《紅樓》風格） | — | [demo](../wenyan-huaben/examples/demo.md) |

### 古典詩詞與新詩格律（4 件）

| skill | 一句話功能 | 強度 | demo |
|---|---|---|---|
| [tang-poem-style](../tang-poem-style/) | 唐詩（五絕 / 七絕 / 五律 / 七律擇一，平仄循譜 + 對仗） | — | [demo](../tang-poem-style/examples/demo.md) |
| [song-ci-style](../song-ci-style/) | 宋詞（5 詞牌選一，豪放 / 婉約擇一 + 選牌邏輯） | — | [demo](../song-ci-style/examples/demo.md) |
| [haiku-style](../haiku-style/) | 日本俳句中譯（季語 + 切字 + 5-7-5；Light / Medium / Heavy 三模式） | Light / Medium / Heavy | [demo](../haiku-style/examples/demo.md) |
| [chinese-sonnet-style](../chinese-sonnet-style/) | 中文十四行詩（馮至標竿；Petrarchan / Shakespearean 二式） | — | [demo](../chinese-sonnet-style/examples/demo.md) |

## 對偶與光譜

- **時代連續軸**：`xianqin → hanwei → guwen → huaben` 構成中文文言四個時代切片
  （諸子 → 史傳 → 古文 → 話本），原文同一篇分別跑這四個 skill 可得「文體歷時光譜」
- **詩詞家族**：`tang-poem` ↔ `song-ci` 是中文古典韻文兩巨頭；`haiku-style`
  是「日本五七五」的中譯版本（家族外成員，但同屬「格律詩詞」 axis）；
  `chinese-sonnet-style` 是現代漢語格律詩，與西方 sonnet 結構接軌
- **散文 vs 韻文**：四 wenyan 是散文；四詩詞是韻文。同分類但是平行兩軸

## 設計原則

- **格律是門檻不是裝飾**：字數、句長、押韻、平仄、對仗等若違規即破譜
- **意象古典化**：現代詞彙（電腦 / 飛機 / 咖啡）一律不入古典文本，做意象搬移
  （飛機 → 舟楫 / 鐵騎、咖啡 → 酒 / 茶）
- **體裁致敬非作者代言**：學形式不抄古人原句

## 邊界案例

- **`chinese-sonnet-style` 是「新詩」而非「古典」**：但因為它是格律鎖死的形式
  （14 行、押韻方案、轉折點），與古典詩詞同屬「形式 lock」軸，故合併進此分類
- **`bagu-essay` 八股文**：雖也是時代體式，但結構鎖死（八段對仗 + 代聖人立言）
  更接近「結構文類」邏輯，歸入「應用與結構文類」
