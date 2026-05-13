# Skills — 中文語體轉換工具集

針對**中文語體、風格、地域變體、歷時風貌、文學體裁**的系統性轉換技能集，
為 [Claude Code](https://docs.anthropic.com/en/docs/claude-code) 及相容
AI 編程助手打造。

目前收錄 **47 個 skill**，依照「**鎖死什麼變數**」分為 8 個分類：

| 分類 | 數 | 鎖死什麼 | 文件 |
|---|---|---|---|
| 文本操作工具 | 5 | 對既有文本做減 / 加 / 重釋 | [docs/01](./docs/01-text-operations.md) |
| 中文地域變體 | 9 | 地理 / 社會語體 | [docs/02](./docs/02-regional-chinese.md) |
| 中英混搭 | 4 | 兩語接觸機制 | [docs/03](./docs/03-cross-tongue.md) |
| 文學作家體 | 9 | 作家個人聲腔 | [docs/04](./docs/04-literary-authors.md) |
| 中文古典體式 | 8 | 時代 + 格律 | [docs/05](./docs/05-classical-forms.md) |
| 應用與結構文類 | 5 | 結構模板鎖死 | [docs/06](./docs/06-applied-closed-form.md) |
| 影視口播 | 2 | 口語媒介 | [docs/07](./docs/07-voice-over.md) |
| 網路文體 | 5 | 網路 meme 句法 | [docs/08](./docs/08-internet-vernacular.md) |

> 想看實際成果?[**exercices-de-style/**](./exercices-de-style/) 用同一篇文章
> （胡適《差不多先生傳》）配多種 skill 改寫，致敬 Raymond Queneau《Exercices
> de Style》。

## 特色

- **強度光譜可控**：歐化處理與地域變體類 skill 提供**輕 / 中 / 重**三段強度，
  依目標 register 選擇（其餘類別為單一目標輸出，不分強度）
- **系統化 checklist**：每個 skill 都有 20-30 項明確規則，每項標記軟硬程度
  與（適用時）啟用強度，可重現、可追溯
- **語言學嚴謹**：明確劃定各 skill 的語言學範疇、引用相關研究（邵敬敏、Jerry
  Norman、胡適等）、以真實語料為範本、**排除 caricature**——把語言變體當真實
  系統對待，不當嘲諷對象
- **體裁致敬非作者代言**：文學體裁類 skill 學的是手法不是字句，不挪用前人原句、
  不寫「魯迅若在會說」式為作家發言

## 安裝

### Prompt 方式

把整個 repo clone 到 `~/.claude/skills/` 或 `<project>/.claude/skills/`，Claude
Code 會自動發現所有 skill：

```bash
git clone https://github.com/tzengyuxio/skills.git ~/.claude/skills
```

### 一行命令

```bash
mkdir -p ~/.claude/skills && cd ~/.claude/skills && git clone https://github.com/tzengyuxio/skills.git .
```

### Marketplace

可從 [Anthropic Skill Marketplace](https://docs.anthropic.com/en/docs/claude-code/skills)
搜尋安裝個別 skill。

## 使用

任一 skill 都可用 `/<skill-name>` 召喚，例如：

```
/lu-xun-style my-article.md
/qiongyao-style 我想把下面這段改成瓊瑤體：...
/tang-poem-style 七律 我的文章在這裡：...
```

詳細用法請看各 skill 的 `README.md` 與 `examples/demo.md`。

## 授權

[MIT License](./LICENSE)

各 skill 內部 SKILL.md 採 `PolyForm Noncommercial 1.0.0`（部分早期 skill 待補
license 欄位）。

---

## 設計理念

- **新 skill 入哪一類**：看 skill 鎖死什麼變數。若鎖死作家聲腔 → 作家體；若鎖死
  地域語體 → 地域變體；若鎖死結構模板 → 結構文類；若是對既有文本做某事 → 操作工具
- **邊界案例**：每份 `docs/` 內有「邊界案例」段落，說明該分類與相鄰分類的劃界
  理由
- **分類有對偶**：dewesternise ↔ westernise（互逆）、gulong ↔ jinyong（武俠對位）、
  prc ↔ roc-bureaucratese（公文時代對偶）、psychoanalytic ↔ postmodern lens（詮釋學
  對位）等
