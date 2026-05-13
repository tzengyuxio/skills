# 文本操作工具 / Text Operations

對既有文本做**減 / 加 / 重釋**三類操作的工具集。**鎖死的不是「文本的身分」**，
而是「對文本做什麼」——這類 skill 不像 `lu-xun-style` 讓文章變成魯迅體，輸出後
仍是「同一個作者寫的同一篇文章」，只是某個維度被改變了。

可組合性高：可串接（先 `humanize` 去 AI 味 → 再 `dewesternise` 去歐化 → 再用
某 lens 重釋）。

## 收錄 skill（5 件）

| skill | 一句話功能 | 強度 | demo |
|---|---|---|---|
| [humanize](../humanize/) | 移除 AI 生成痕跡（浮誇用詞、tricolon、虛主語、空排比） | — | [demo](../humanize/examples/demo.md) |
| [dewesternise](../dewesternise/) | 去歐化（被動 / 抽象主語 / 性 / 們 / 地 過用等 25 項） | 輕 / 中 / 重 | [demo](../dewesternise/examples/demo.md) |
| [westernise](../westernise/) | 反向加歐化（互逆操作 — 把中文寫成翻譯腔） | 輕 / 中 / 重 | [demo](../westernise/examples/demo.md) |
| [psychoanalytic-lens](../psychoanalytic-lens/) | 精神分析重釋（Freud / Lacan 框架重寫敘述動因） | — | [demo](../psychoanalytic-lens/examples/demo.md) |
| [postmodern-lens](../postmodern-lens/) | 後現代重釋（元敘事懷疑 / 競爭版本 / 敘述者插話） | — | [demo](../postmodern-lens/examples/demo.md) |

## 對偶與光譜

- **dewesternise ↔ westernise**：互為逆操作。同一篇文章順向逆向各跑一次，可做
  「歐化迴圈」實驗
- **humanize vs dewesternise**：邊界明確。humanize 處理「**AI 味**」（浮誇 /
  tricolon / 虛主語）；dewesternise 處理「**歐化**」（被動 / 抽象主語 / 長前飾）。
  兩者重疊度低，可串用
- **psychoanalytic ↔ postmodern lens**：兩種詮釋學的對位 — 一個追深層動因（無意識
  / 欲望結構），一個拒絕深層說（元敘事懷疑）。改寫同一篇文章，兩個 lens 會給出
  完全不同的版本

## 設計原則

- 操作工具不給文本一個「身分」，輸出後仍是「原作者的同一篇文章」修正版
- 可組合性高，建議串接使用
- Lens 類採 A 路線（重寫敘事內部動因 / 意義句），不採 B 路線（原文 + 外部評論）
