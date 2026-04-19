# Examples

本目錄收錄各 skill 的**公開示範**與**共用源文**。

## 目錄結構

- [`source-texts/`](./source-texts/) — 共用源文庫，供各 skill 展示使用
  - [`mr-chabuduo.md`](./source-texts/mr-chabuduo.md) — 差不多先生傳（胡適, 1924，公有）
  - [`little-prince.md`](./source-texts/little-prince.md) — 小王子片段（英文）
  - [`weather-rain.md`](./source-texts/weather-rain.md) — 雨天故事（自編）

各 skill 的 demo 檔案位於該 skill 資料夾下的 `examples/demo.md`（或類似命名），連結可在 repo 根目錄 [README](../README.md) 的 skill 列表中找到。

## 和 `test-samples/` 的差別

| 目錄 | 用途 | 版控 |
|------|------|------|
| `examples/` | 公開示範，展示 skill 效果 | **committed** |
| `test-samples/`（各 skill 下以及 repo root） | 本地實驗、含設計註記的內部測試 | **gitignored** |

公開示範維持乾淨格式：只有源文 + 輸出，不混入應用規則、強度分析等開發過程資訊。
