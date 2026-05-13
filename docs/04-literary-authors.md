# 文學作家體 / Literary Author Voices

把文章改寫成**某位作家或某種翻譯傳統的聲腔**。**鎖死的是「作家個人 / 譯本傳統
的特徵性句法、用詞、節奏」**——讀者一打開就認出「這是某某的口吻」。

涵蓋中文現代文學（魯迅、張愛玲、余光中、瓊瑤）、武俠（古龍、金庸）、中譯西洋
文學（朱生豪式莎劇、海明威中譯、福爾摩斯維多利亞偵探）。

## 收錄 skill（9 件）

| skill | 一句話功能 | 強度 | demo |
|---|---|---|---|
| [lu-xun-style](../lu-xun-style/) | 魯迅體（文白夾雜、標誌虛詞、冷峻反諷、無標籤距離） | — | [demo](../lu-xun-style/examples/demo.md) |
| [eileen-chang-style](../eileen-chang-style/) | 張愛玲體（蒼涼基調、月光鏡子絲綢意象、細節暴力） | — | [demo](../eileen-chang-style/examples/demo.md) |
| [yu-guangzhong-style](../yu-guangzhong-style/) | 余光中散文（文白交織、長句鋪排、古典化用、地理錨點） | — | [demo](../yu-guangzhong-style/examples/demo.md) |
| [qiongyao-style](../qiongyao-style/) | 中期瓊瑤愛情敘事（必有阻礙 + 痛感收尾） | — | [demo](../qiongyao-style/examples/demo.md) |
| [gulong-style](../gulong-style/) | 中後期古龍武俠（極短句 + 警句嵌入 + 對比張力） | — | [demo](../gulong-style/examples/demo.md) |
| [jinyong-style](../jinyong-style/) | 中期金庸武俠（章回史傳氣 + 招式詳寫 + 詩詞嵌入） | — | [demo](../jinyong-style/examples/demo.md) |
| [shakespeare-style](../shakespeare-style/) | 朱生豪式中譯莎劇腔（半文白戲劇 + 譬喻密度 + 獨白） | 輕 / 中 / 重 | [demo](../shakespeare-style/examples/demo.md) |
| [hemingway-style](../hemingway-style/) | 海明威體中譯版（冰山理論 + 短句 + 重複錨定 + 翻譯腔為 feature） | — | [demo](../hemingway-style/examples/demo.md) |
| [sherlock-holmes-style](../sherlock-holmes-style/) | 朱生豪式中譯維多利亞偵探腔（華生回憶體 + 演繹獨白 + 案件三幕） | 輕 / 中 / 重 | [demo](../sherlock-holmes-style/examples/demo.md) |

## 對偶與光譜

- **武俠雙絕**：`gulong-style` ↔ `jinyong-style` 8 軸對偶（極短句 vs 章回長句、
  警句嵌入 vs 招式詳寫、留白 vs 鋪陳）— 兩者刻意設計為對位
- **中譯西洋三件套**：`shakespeare-style` / `hemingway-style` / `sherlock-holmes-style`
  共享「中譯西洋文體致敬」的軸線，世界觀必走西洋通名禁中華具體位移（嘉興 →
  薩塞克斯、廟祝 → 教區牧師等）。歐化句法是 feature 不是 bug
- **散文 vs 小說**：`yu-guangzhong-style` 是散文軸；其餘八件是小說 / 戲劇軸

## 設計原則

- 每個 skill 必有「風格參照」段，引用代表作（例如張愛玲〈金鎖記〉〈傾城之戀〉
  〈封鎖〉），並含真實原文短引
- **體裁致敬 vs 作家代言**：本類 skill 是體裁致敬，不是讓 AI「假裝是某作家在寫」。
  不挪用作家原句、不寫「魯迅若在會說」式自命為作家發言
- 諷刺對象（若有）限抽象普世（國民性 / 看客 / 苟且），不指涉特定真人

## 邊界案例

- **`sherlock-holmes-style` 含案件三幕結構**——介於「作家體」與「結構文類」之間。
  本類收錄是因為主軸是「華生第一人稱回憶 + 朱生豪式中譯腔」，voice 主導，form
  附帶
- **`bagu-essay` / `liaozhai-tale` / `koanify`** 雖在文學體裁但結構鎖死強於聲腔
  特徵，歸入「應用與結構文類」分類

## 後續候選

- 林志玲體（已評估不做，caricature 風險）
- domineering-ceo-romance（霸總羅曼史，roadmap 第二梯隊）
- xianxia-wenwang（玄幻網文，roadmap 第二梯隊）
