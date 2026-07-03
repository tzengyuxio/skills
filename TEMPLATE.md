# Skill Template — 製作新 skill 的規範

本檔規範本 repo 所有 skill 的標準結構與寫作慣例，適用於**新製作的 skill** 與
**逐步修正的既有 skill**。

## 目錄結構

```
<skill-name>/                  # 名稱 kebab-case,與 SKILL.md 的 name 欄位一致
├── SKILL.md                   # 必有,Claude Code 載入入口
├── README.md                  # 必有,GitHub 顯示與 skill 自我介紹
├── examples/                  # 必有
│   └── demo.md                # 必有，共用源文的改寫示範
└── references/                # 可選，放原文參照樣本
    └── *.md
```

**禁止 commit**:
- `test-samples/`(本地測試輸出)— 屬於開發階段資料，放 repo 根目錄
  `test-samples/`(已 gitignore)
- `evals/`(evaluation runs 輸出)— 同上
- `.DS_Store`、`*.swp` 等系統 / 編輯器檔

## SKILL.md frontmatter

```yaml
---
name: <skill-name>                          # 必，與目錄名一致(kebab-case)
description: >                              # 必，英文,3-8 行(過長會被 LLM
                                            # 抽取重點時截斷)。包含:
  <one-line: what this skill transforms text into>.
  <one-line: when this skill activates / what triggers it>.
  Triggers on "/<skill>", "<phrase 1>", "<phrase 2>", ...
license: PolyForm Noncommercial 1.0.0       # 必，所有 skill 統一
argument-hint: "[file-path]"                # 必，標示參數
allowed-tools: Read, Write, Edit, Glob      # 必，通常這四個；有 WebFetch 時加上
---
```

**寫 description 的要點**:
- 第一句說「做什麼」(transformation 動作 + 目標體式)
- 第二句說「何時觸發」(在什麼情境用)
- 列舉觸發 phrase(中英雙語都列,Claude Code 會用這些做 skill discovery)
- 避免內部術語(讀者是 Claude Code 的 skill router,不是已熟悉 repo 的人)

## SKILL.md 本體 section 順序

固定順序如下,**每個 skill 必含 1-9,選用 10-11**:

1. `# <Skill-Name> — <一句話中文功能>`(H1 標題,Title Case 名稱 + 全形破折號 + 中文)
2. **介紹段**(1-2 段散文，說明做什麼)
3. `風格參照`(若有真實作家 / 文體 / 風格依據，列代表作)— 可選但鼓勵
4. `## 一句話靈魂`(該 skill 的核心定位，單句)
5. `## Arguments`(`$0` 等參數說明)
6. `## Step 1: Load the Text` 到 `## Step N-1: <最後一步>` — 操作流程
7. `## Step N: Standard Punctuation + Self-check`(全形標點 + 機械自檢指令)
8. `## Step N+1: Self-check Against Checklist`(逐條對照 Hard checklist)
9. `## Hard Checklist`(C / S / V / M 四類，合計 ~21 條)
10. `## Anti-patterns`(可選但鼓勵,~9 條典型失誤)
11. `## 強度模式` / `## 強度三級`(若有 Light/Medium/Heavy 或 Solo/Duo 才寫)
12. `## Scope Boundary`(可選但鼓勵 — 「想做 X 用哪個 skill」對照表)
13. `## Important Notes`(可選)

### H1 標題格式

統一為 `# <Title-Cased-Name> — <一句話中文功能>`:

- ✅ `# Humanize — 去除 AI 寫作痕跡`
- ✅ `# Lu Xun-style — 改寫成魯迅體`
- ❌ `# humanize — Remove AI Writing Patterns`(名稱要 Title Case、副標應中文)
- ❌ `# laogao-style — ...`(`L` 應大寫)

### Checklist 命名

**文體 skill**(literary author / 中文古典體式 / 應用與結構文類 / 影視口播 /
網路文體 / 詮釋 lens 等)採 **C / S / V / M** 四類:
- **C (Concrete)**:具體意象、物件、稱謂、地名等可數對象
- **S (Surface)**:句法、標點、字數、格律等表層形式
- **V (Voice)**:敘述視角、語氣、派別、聲腔特徵
- **M (Meta)**:結構、收束、不變條件、自檢規範

**操作 / 地域變體 / 跨語混搭 skill** 用領域對應字母，語意上更精準，不強制改為 C/S/V/M:
- `humanize`:**C** (Content)/ **S** (Structure)/ **V** (Vocabulary)/ **M** (Meta)
  — 注意這裡的 C 是 Content patterns,**與文體 skill 的 C (Concrete) 同字母不同義**
- `dewesternise` / `westernise`:**G** (Grammar)/ **V** (Vocabulary)/ **S** (Structure)
- 地域變體(taiwan-mandarin / dongbei-mandarin 等):**G** (Grammar)/ **P** (Particles)
  / **L** (Lexicon)/ **S** (Structure)等，各依該語言變體實際軸線

**M 類(或語意對等類)最末條必為「全形標點零違規」+ 對應 Step 的自檢指令** —— 三件套
(Hard rule + 機械自檢 + Anti-pattern)是所有純 CJK 輸出 skill 的鐵律。

**新製作的 skill 入哪套?** 依 skill 「鎖死什麼變數」(見根 `README.md` 的 8 分類框架):
- 鎖死作家聲腔 / 體裁 / 詩詞格律 / 結構模板 / 媒介 / meme 句法 → C/S/V/M
- 鎖死語言變體 / 兩語接觸 / 對文本做特定處理 → 領域對應字母

## examples/demo.md 規範

(已在 memory `feedback_demo_design.md` 確立)

- 至少 3 個 demo,共享源文於 repo 根 `examples/source-texts/`
- **不共用發明骨架**:多 demo 共用源文時，每個 demo 自己從源文長出不同結構,
  禁複用前一 demo 的骨架
- **結尾留餘韻**:demo 結尾就是 skill 的輸出本身,**不附評論**(「這個範例展示了
  X」之類禁止)
- 不放對照表 / 不放成功 vs 失敗版標籤 / 不跨 skill 比較
- 每個 demo 須包含:
  - 源文連結(`../../examples/source-texts/<source>.md`)
  - 改寫過程筆記(可選，簡短表格說明 Step 2-4 的選擇)
  - 改寫後成品

## README.md(每個 skill 內)

**獨立於 SKILL.md** — SKILL.md 是給 Claude Code 載入用,README.md 是給人看用。

- 中文撰寫
- 主要 section(可調整，但下列必含 ≥ 3 個):
  - 技能說明
  - 主要規則(精簡列舉，不抄 SKILL.md 全部 21 條)
  - 風格參照原作
  - 強度模式說明(若有)
  - 何時用 / 何時不用(可選)
  - demo 連結
- 不抄 SKILL.md 全文，寫成「讀者導向」版本
- 行數參考:150-250 行

## references/(可選)

放真實原作參照樣本，供 LLM 在執行 skill 時參照風格座標。

- 命名:`source-passages.md`(主要原作短引)、`<topic>.md`(專題參照)
- 內容須清楚標示版權狀態(若為公有領域、引用研究、合理使用範圍)

## 全形標點自檢(必含)

純 CJK 輸出的 skill 必須在 SKILL.md 某 Step 含:

```bash
python3 -c "
import re, sys
text = open(sys.argv[1]).read()
bad = re.findall(r'[^\x00-\x7f][,;:?!][^\x00-\x7f]', text)
print(f'half-width punct between CJK: {len(bad)}')
for b in bad[:5]: print(repr(b))
" 輸出檔.md
```

對含 ASCII 字符的 skill(jingjing / chinglish / written-hokkien 等),調整正則為
CJK 相鄰版 `r'[一-鿿㐀-䶿][,;:?!][一-鿿㐀-䶿]'` 或人工確認。

詳見 memory `feedback_skill_output_punctuation.md` 的「自檢正則的彈性」段。

## 新增 skill 入哪個分類

依照「鎖死什麼變數」入 8 分類之一(見根 `README.md` 與 `docs/01-08*.md`):

| 鎖死的變數 | 入哪個分類 |
|---|---|
| 對既有文本做減 / 加 / 重釋 | 01 文本操作工具 |
| 地理 / 社會語體 | 02 中文地域變體 |
| 兩語接觸機制 | 03 中英混搭 |
| 作家個人聲腔 | 04 文學作家體 |
| 時代 + 格律 | 05 中文古典體式 |
| 結構模板鎖死 | 06 應用與結構文類 |
| 口語媒介 | 07 影視口播 |
| 網路 meme 句法 | 08 網路文體 |

加入新 skill 時須**同時更新**:
- 該 skill 自己的 SKILL.md / README.md / examples/
- `docs/0X-<category>.md`(加一列入 skill 表)
- 根 `README.md`(更新數量欄位)

## 製作前 web research(必做)

製作風格 / 文體 / 作家 / lens 類 skill 時，規則 / 概念 / 指紋必上網查證一手資料,
不可只依 LLM 內部知識。詳見 memory `feedback_skill_web_research.md`。

## 中譯西洋文體禁中華世界觀位移

shakespeare-style / hemingway-style / sherlock-holmes-style / yizhi-style 等中譯
西洋文體 skill,世界觀層必走西洋通名(古城 / 王命 / 使者 / 聖像),不可換為
中華具體專名(嘉興 / 湖廣 / 廟祝 / 朝廷敕令 / 銀針)。源文若是中華情境，須做
雙重位移。詳見 memory `feedback_translated_western_setting.md`。

## 中譯文體不禁歐化翻譯腔

中譯西洋文學類 skill 不應將歐化句法列為違規,**翻譯感是 feature 不是 bug**。
詳見 memory `feedback_translation_flavor.md`。

## 致敬活躍創作者的鐵律組

若為致敬活躍 / 爭議創作者類 skill(如 laogao-style),命名可致敬，但**輸出層
必須中性化**,並設四條鐵律組(M-01/M-02/M-03/M-05/M-08)切割語體致敬與爭議實踐。
詳見 memory `feedback_active_creator_tribute_iron_rules.md`。
