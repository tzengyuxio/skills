# Hanjify — 英語漢字化

將英文文本轉換為漢字化英語——以 CJK 漢字承載語意，保留英語文法結構不變。

## 功能說明

Hanjify 將英文單詞替換為漢字（Hanzi/Kanji/Hanja），同時完整保留英語的文法、語序、標點與空格。採用日文送假名（okurigana）風格的形態學機制：漢字表示詞根，英文後綴以羅馬字母直接附加（如 動ing、美ful、思er）。

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
> 一度 當 我 是ed 六 年s 古 我 見t 一 壮麗 絵 在 一 書 関於 其 密林.

**Ruby:**
> <ruby>一度<rt>Once</rt></ruby> <ruby>當<rt>when</rt></ruby> <ruby>我<rt>I</rt></ruby> <ruby>是ed<rt>was</rt></ruby> <ruby>六<rt>six</rt></ruby> <ruby>年s<rt>years</rt></ruby> <ruby>古<rt>old</rt></ruby> <ruby>我<rt>I</rt></ruby> <ruby>見t<rt>saw</rt></ruby> <ruby>一<rt>a</rt></ruby> <ruby>壮麗<rt>magnificent</rt></ruby> <ruby>絵<rt>picture</rt></ruby> <ruby>在<rt>in</rt></ruby> <ruby>一<rt>a</rt></ruby> <ruby>書<rt>book</rt></ruby> <ruby>関於<rt>about</rt></ruby> <ruby>其<rt>the</rt></ruby> <ruby>密林<rt>jungle</rt></ruby>.

## 核心設計

- **不是翻譯** — 英語文法完全保留，只替換個別單詞為漢字
- **送假名形態學** — 漢字詞根＋羅馬後綴（動s、動ed、動ing、思t）
- **80+ 固定功能詞** — 冠詞、代名詞、介詞等有嚴格對照表，確保一致性
- **泛 CJK 選字** — 混用中日韓漢字與古字，不偏向任何單一傳統
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
