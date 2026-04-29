# Hanjify — 英語漢字化

將英文文本轉換為漢字化英語——以 CJK 漢字承載語意，保留英語文法結構不變。

> **規範來源**：本 skill 依 [tzengyuxio/hanjify 的 docs/spec.md](https://github.com/tzengyuxio/hanjify/blob/main/docs/spec.md) 實作（[線上工具](https://hanjify.tzengyuxio.me)）。skill 與網頁工具共享規範，差異在 skill 可上下文判斷多義字、查表工具不行。

## 功能說明

Hanjify 將英文單詞替換為漢字（Hanzi/Kanji/Hanja），同時完整保留英語的文法、語序、標點與空格。採用混合形態學：屈折變化（`-s/-ed/-ing/-er/-est`）保留羅馬字、派生變化（`-er(者)/-ly(地)/-ful(的)/un-(不)/re-(再)` 等）轉漢字。

轉換結果既不是英文、也不是中文或日文，而是一套獨特的「架空歷史」書寫系統——彷彿英語使用者在歷史上獨立發展出了漢字書寫。

## 安裝

一行安裝（clone + 複製）：

```bash
git clone --depth 1 https://github.com/tzengyuxio/skills.git /tmp/tz-skills && mkdir -p ~/.claude/skills && cp -r /tmp/tz-skills/hanjify ~/.claude/skills/ && rm -rf /tmp/tz-skills
```

手動安裝（已 clone 的情況）：

```bash
cp -r hanjify ~/.claude/skills/hanjify
```

## 使用方式

```
/hanjify path/to/article.md
```

**觸發詞：** `/hanjify`、"hanjify this"、"convert to hanzi"、"英語漢字化"、"漢字化"

## 輸出格式

三個版本輸出至同一檔案：

- **Hanjified** — 純漢字＋羅馬後綴（無英文原文）
- **Ruby** — HTML ruby 標注，附英文原文讀音
- **Original** — 原始英文，完全不變

## 範例

**Original:**
> Once when I was six years old I saw a magnificent picture in a book about the jungle.

**Hanjified:**
> Once 当 予 是ed 六 年s 古 予 見t a 壮麗 絵 in a 書 関於 the 密林.

**Ruby:**
> <ruby>一度<rt>Once</rt></ruby> <ruby>当<rt>when</rt></ruby> <ruby>予<rt>I</rt></ruby> <ruby>是ed<rt>was</rt></ruby> <ruby>六<rt>six</rt></ruby> <ruby>年s<rt>years</rt></ruby> <ruby>古<rt>old</rt></ruby> <ruby>予<rt>I</rt></ruby> <ruby>見t<rt>saw</rt></ruby> a <ruby>壮麗<rt>magnificent</rt></ruby> <ruby>絵<rt>picture</rt></ruby> in a <ruby>書<rt>book</rt></ruby> <ruby>関於<rt>about</rt></ruby> the <ruby>密林<rt>jungle</rt></ruby>.

> 註：`a / an / the / of / in / to / on / at` 為不轉清單條目，保留為英文。

> 完整示範（多段源文 × 三格式輸出）請見 [examples/demo.md](./examples/demo.md)。

## 核心設計

- **不是翻譯** — 英語文法完全保留，只替換個別單詞為漢字
- **混合形態學** — 屈折保留羅馬字（動s、動ed、動ing）、派生轉漢字（教者、實際地、美的）
- **140+ 功能詞嚴格對照表** — 代名詞、助動詞、介詞等定義於 spec.md §3
- **不轉清單** — 純虛詞 `a/an/the/of/in/to/on/at` 保留英文
- **泛 CJK 選字** — 採三地通用優先，繁體基底＋簡化／古字／日文新字體採用清單
- **英文慣例** — 標點與空格遵循英文，不使用中文標點

## 背景

基於 [HANJIFY 網頁工具](https://hanjify.tzengyuxio.me)，該工具透過 4,792 筆人工策劃的詞表進行逐字查表替換。本 skill 將同一概念改以 LLM 驅動，實現無限詞彙覆蓋、形態一致性、以及上下文感知的選字能力。

設計原則詳見原工具 FAQ：
1. **保持英語本質** — 漢字化不是翻譯，英語是基礎
2. **中立歷史背景** — 選字不限於中日，涵蓋韓國漢字與古字
3. **詞語構建** — 模擬英語母語者查字典造詞的視角
4. **開放討論** — 歡迎更好的選字建議

## 相關 Skills

- [dewesternise](../dewesternise/) — 去除中文歐化痕跡
- [westernise](../westernise/) — 刻意加入翻譯腔
- [humanize](../humanize/) — 去除 AI 寫作痕跡
