# Skills — 中文語體轉換工具集

針對**中文語體、風格、地域變體、歷時風貌**的系統性轉換技能集，為 [Claude Code](https://docs.anthropic.com/en/docs/claude-code) 及相容 AI 編程助手打造。

涵蓋四條中文語體軸：

- **人類書寫 ↔ AI 寫作痕跡**（[humanize](./humanize/)）
- **自然中文 ↔ 歐化翻譯腔**（[dewesternise](./dewesternise/) / [westernise](./westernise/)）
- **標準華語 ↔ 地域變體**（[taiwan-mandarin](./taiwan-mandarin/) / [hongkong-chinese](./hongkong-chinese/) / [singapore-mandarin](./singapore-mandarin/)）
- **現代中文 ↔ 歷代文言**（[wenyan-xianqin](./wenyan-xianqin/) / [hanwei](./wenyan-hanwei/) / [guwen](./wenyan-guwen/) / [huaben](./wenyan-huaben/)，跨約 2500 年）

外加三個中英混搭工具：[chinglish](./chinglish/)、[singlish](./singlish/)、[hanjify](./hanjify/)。

> [English version](./README_EN.md)

## 特色

- **強度光譜可控**：多數 skill 提供**輕／中／重**三段強度，使用者依目標 register 選擇；不是一刀切的單一輸出
- **系統化 checklist**：每個 skill 都有 20-30 項明確規則，每項標記軟硬程度與啟用強度（如 `[Hard, Medium+]`），可重現、可追溯
- **語言學嚴謹**：明確劃定各 skill 的語言學範疇、引用相關研究（邵敬敏、Jerry Norman、胡適等）、以真實語料為範本、**排除 caricature**——把語言變體當真實系統對待，不當嘲諷對象
- **逆操作對偶、可組合**：`dewesternise` ↔ `westernise` 互為反向；skills 可串接使用（如 `dewesternise` → `taiwan-mandarin`）
- **公開示範與本地實驗分離**：各 skill 的 [`examples/`](./examples/) 收錄乾淨展示，共用 [`examples/source-texts/`](./examples/source-texts/) 源文庫讓各 skill 可橫向比較

## 可用技能

### AI 寫作風格處理

| 技能 | 功能 |
|------|------|
| [humanize](./humanize/) | 去除 AI 生成文字的寫作痕跡（26 項 checklist，支援中英文） |

### 翻譯腔處理

針對中文「歐化」（翻譯腔）現象的風格轉換工具，各附 25 項 checklist，互為逆操作。

| 技能 | 功能 |
|------|------|
| [dewesternise](./dewesternise/) | 去除中文的歐化寫法（被動句、抽象主語、長前飾語等） |
| [westernise](./westernise/) | 刻意加入翻譯腔（支援輕／中／重三段強度） |

### 中英語言混搭

英語變體與書寫系統轉換工具——將文字轉為各種受華語影響的英語風格或混合書寫系統。

| 技能 | 功能 |
|------|------|
| [chinglish](./chinglish/) | 將中文或英文轉為中式英語（Chinglish）——重現母語干擾下的系統性變異 |
| [singlish](./singlish/) | 將任何文字轉為新加坡式英語（Singlish）——融合閩南語、馬來語的克里奧爾語言 |
| [hanjify](./hanjify/) | 將英文轉換為漢字化英語——漢字承載語意，保留英語文法（送假名風格形態學） |

### 地域中文變體

將文字轉為不同華語社群的在地口語/書面變體，各附 checklist 與輕／中／重三段強度。

| 技能 | 功能 | 範例 |
|------|------|------|
| [taiwan-mandarin](./taiwan-mandarin/) | 將文字轉為台灣國語——融合台語/日語借詞、擬音字（偶/粉/素/降）、注音文、語尾助詞（啦/喔/齁/耶） | [demo](./taiwan-mandarin/examples/demo.md) |
| [hongkong-chinese](./hongkong-chinese/) | 將文字轉為港式中文——港式詞彙（巴士/的士/雪櫃）、港式音譯（荷里活/梳化/三文治）、中英夾雜、詞序倒置；Heavy 模式可涵蓋完整粵語書面化（係/唔/嘅/咗/佢/呢/嗰） | [demo](./hongkong-chinese/examples/demo.md) |
| [singapore-mandarin](./singapore-mandarin/) | 將文字轉為新加坡華語——SG 行政生活詞（組屋/德士/樂齡/客工）、閩南語借詞（幾時/不懂/做工/怕輸）、馬來語借詞（甘榜/巴剎/atas/bodoh）、先後置句式、千-單位數字；與 singlish 共構 SG 雙胞胎 | [demo](./singapore-mandarin/examples/demo.md) |

### 應用文類

中文特定應用文體的制度化風格轉換。目前收錄兩種公文體，預留擴充給其他應用文類型（書信、啟事、契約、會議紀錄、自傳等）。

| 技能 | 功能 | 範例 |
|------|------|------|
| [prc-bureaucratese](./prc-bureaucratese/) | 將文字轉為中共黨政公文體——高頻動詞（落實/加強/推進/深化）、副詞堆疊（紮實推進/深入貫徹/全面落實）、四字格對偶（不忘初心、牢記使命）、數字化政治套語（四個全面/五位一體）、新時代意識形態詞彙 | [demo](./prc-bureaucratese/examples/demo.md) |
| [roc-bureaucratese-classic](./roc-bureaucratese-classic/) | 將文字轉為 1960-80 年代中華民國公文體——文言單字（之/於/以/係/為/俾/爰）、文言連接詞（茲/惟/嗣/俟/頃）、階層敬語（鈞/貴/本/職/台端）、程序套語（查照/鑒核/核備/奉悉）、主旨-說明-辦法格式 | [demo](./roc-bureaucratese-classic/examples/demo.md) |

### 文言文改寫

將現代中文改寫為不同時期的文言風格，各附 20-22 項 checklist。

| 技能 | 風格 | 代表作品 |
|------|------|---------|
| [wenyan-xianqin](./wenyan-xianqin/) | 先秦諸子體 | 論語、莊子、韓非子 |
| [wenyan-hanwei](./wenyan-hanwei/) | 漢魏史傳體 | 史記、漢書、三國志 |
| [wenyan-guwen](./wenyan-guwen/) | 唐宋古文體 | 韓愈、蘇軾、歐陽修 |
| [wenyan-huaben](./wenyan-huaben/) | 話本小說體 | 水滸傳、三國演義、紅樓夢 |

## 安裝方式

### 請 AI 幫你安裝

將以下 prompt 貼給你的 AI 助手（Claude Code、Cursor、Windsurf 等）：

```
請從 https://github.com/tzengyuxio/skills 安裝 humanize 技能到我的全域 skills
目錄（~/.claude/skills/）。用 git clone --depth 1 下載後，只複製需要的技能
資料夾，最後清理暫存檔。
```

將 `humanize` 替換為上表中任意技能名稱。若要安裝到目前專案，將路徑改為 `.claude/skills/`。

### 一行安裝

```bash
git clone --depth 1 https://github.com/tzengyuxio/skills.git /tmp/tz-skills \
  && mkdir -p ~/.claude/skills \
  && cp -r /tmp/tz-skills/humanize ~/.claude/skills/ \
  && rm -rf /tmp/tz-skills
```

將 `humanize` 替換為任意技能名稱，或一次列出多個（如 `dewesternise westernise`）。若要安裝到專案，將 `~/.claude/skills` 改為 `.claude/skills`。

### Plugin Marketplace

```
/plugin marketplace add tzengyuxio/skills
/plugin install humanize@tzengyuxio-skills
```

## 授權

MIT
