# Skills

為 [Claude Code](https://docs.anthropic.com/en/docs/claude-code) 及相容 AI 編程助手打造的自訂技能集。

每個技能是一個獨立資料夾，內含 `SKILL.md`，用來教導 AI 助手執行特定的文字處理任務。

> [English version](./README_EN.md)

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

| 技能 | 功能 |
|------|------|
| [taiwan-mandarin](./taiwan-mandarin/) | 將文字轉為台灣國語——融合台語/日語借詞、擬音字（偶/粉/素/降）、注音文、語尾助詞（啦/喔/齁/耶） |
| [hongkong-chinese](./hongkong-chinese/) | 將文字轉為港式中文——港式詞彙（巴士/的士/雪櫃）、港式音譯（荷里活/梳化/三文治）、中英夾雜、詞序倒置；Heavy 模式可涵蓋完整粵語書面化（係/唔/嘅/咗/佢/呢/嗰） |

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
