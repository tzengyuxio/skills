# Humanize — 去除 AI 文風

移除 AI 生成文的寫作痕跡，改寫為自然、像人寫的文字。

## 什麼是 AI 文風？

AI 生成文（尤其是 LLM 寫的長文）往往帶有辨識度很高的文體特徵：宏大化的開場、空洞的總結、模糊的歸因（「許多專家認為」）、三元排比濫用、AI 簽名詞彙（「不僅…更…」「值得關注」）、機械化的條列與粗體強調、以及段末的「展望」「未來可期」。這些模式單獨看不致命，堆在一起就會讓讀者立刻察覺「這是 AI 寫的」。

維基百科社群已整理出《AI 生成文的特徵》與《Signs of AI writing》兩份指南，本 skill 的 checklist 即以此為骨幹，再加入中文寫作的在地觀察。

## 功能

掃描文字中的 AI 寫作特徵，然後改寫為自然的人類文字。

26 項 checklist，分為 Content (C1–C7)、Structure (S1–S8)、Vocabulary (V1–V6)、Meta (M1–M4) 四大類，每項標記 Hard flag（幾乎確定 AI）或 Soft flag（AI 愛用但人也會寫），附 Before/After 範例。

主要服務繁體中文寫作，但 checklist 與原則適用任何語言。

## 安裝

一行安裝（clone 並複製到本機 skills 目錄）：

```bash
git clone --depth 1 https://github.com/tzengyuxio/skills.git /tmp/tz-skills && mkdir -p ~/.claude/skills && cp -r /tmp/tz-skills/humanize ~/.claude/skills/ && rm -rf /tmp/tz-skills
```

或透過 Claude Code 的 plugin marketplace：

```
/plugin marketplace add tzengyuxio/skills
/plugin install humanize@tzengyuxio-skills
```

手動安裝（若已 clone）：

```bash
cp -r humanize ~/.claude/skills/humanize
```

## 使用方式

```
/humanize path/to/article.md
```

也可以在剛寫完或編輯完一份 markdown 後直接無參數呼叫，對當前上下文中的檔案處理。

**觸發詞：** `/humanize`、「make it sound human」、「remove AI tone」、「去 AI 味」、「寫得更像人」、「降低 AI 感」

## 運作流程

1. **掃描** — 逐項比對 26 項 AI 寫作特徵，標記 Hard flag 與 Soft flag 段落
2. **報告** — 以表格呈現問題位置、類型、說明
3. **改寫** — 依 13 條改寫原則與「個性與語氣」指引重寫標記段落
4. **審查** — 二輪反 AI 自檢：重掃 checklist + 「還有哪裡感覺像 AI？」直覺檢查
5. **輸出** — 另存為 `_clean` 後綴新檔（如 `article_clean.md`），保留原檔供對照

## 模式分類

| 類別 | 編號 | 內容 |
|------|------|------|
| Content | C1–C7 | 宏大化開場、空洞總結、模糊歸因、浮面分析、宣傳語氣、細節退化、諂媚語氣 |
| Structure | S1–S8 | 三元排比濫用、否定式排比、公式化結尾、機械化條列、粗體浮濫、破折號過用、「儘管…仍…」公式、假範圍 |
| Vocabulary | V1–V6 | LLM 簽名詞彙、對沖語過用、避用繫詞「是」、同義詞輪替、分詞鏈、填充語 |
| Meta | M1–M4 | 聊天機器人殘跡、散文中的 emoji、把編號段落當散文、markup 殘跡 |

每一項都附 Before/After 範例，示範預期的改寫結果。

## 改寫原則

1. 具體取代籠統
2. 展示而非宣告
3. 平鋪取代層層拔高
4. 只下有憑有據的結論
5. 歸因要點名，不然就刪掉
6. 句式要有變化
7. 允許不完美
8. 用平常的詞
9. 粗體標結構，不標語氣
10. 散文優先於條列
11. 自然重複（不要換同義詞輪流用）
12. 用簡單動詞（「是」優於「作為」）
13. 保留鋒利的細節（不要磨平具體描述）

另附「個性與語氣」章節，供散文與評論類文字注入人味：變化節奏、承認複雜、允許第一人稱、相信讀者、去掉客套開場。

## Changelog

### v3 — 2026-03-29

- 為每一項模式加上 Before/After 範例
- 新增「個性與語氣」章節，清理完之後再注入人味
- 升級自檢為兩輪反 AI 審查（checklist 重掃 + 直覺檢查）
- 新增 3 項模式：C7（諂媚語氣）、S8（假範圍）、V6（填充語）
- 總計：26 項模式、13 條改寫原則

### v2 — 2026-03-29

- 新增 7 項模式：C6（細節退化）、S6（破折號過用）、S7（「儘管」公式）、V3（避用繫詞）、V4（同義詞輪替）、V5（分詞鏈）、M4（markup 殘跡）
- 擴充 V1 簽名詞庫（中英文）
- 將 S2 拆成兩種變體：否定再定義 vs 層層拔高
- 新增 3 條改寫原則：自然重複、簡單動詞、保留鋒利細節
- 新增自檢步驟
- 新增英文維基百科參考

### v1 — 2026-03-29

- 初版：16 項模式（C1–C5、S1–S5、V1–V2、M1–M3）與 10 條改寫原則

## 參考資料

- [Wikipedia：AI 生成文的特徵](https://zh.wikipedia.org/wiki/Wikipedia:AI%E7%94%9F%E6%88%90%E6%96%87%E7%9A%84%E7%89%B9%E5%BE%B5) — 中文維基社群整理的 AI 生成文辨識指南
- [Wikipedia：Signs of AI writing](https://en.wikipedia.org/wiki/Wikipedia:Signs_of_AI_writing) — 英文維基對應條目
- [blader/humanizer](https://github.com/blader/humanizer) — 英文為主的 humanizer skill，本 skill 的個性／語氣章節與 before/after 範例格式受其啟發
- [op7418/Humanizer-zh](https://github.com/op7418/Humanizer-zh) — blader/humanizer 的簡體中文改編版

## 相關技能

- [dewesternise](../dewesternise/) — 去除歐化中文（翻譯腔），處理句法層面的西化
- [westernise](../westernise/) — 逆操作：刻意加入翻譯腔
