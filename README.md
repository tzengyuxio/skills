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
