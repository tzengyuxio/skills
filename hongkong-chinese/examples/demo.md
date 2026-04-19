# Hong Kong Chinese — 示範

展示 `hongkong-chinese` skill 在不同強度下的輸出效果。源文來自 [`examples/source-texts/`](../../examples/source-texts/)。

---

## 範例一：雨天故事（中文源）

源文：[weather-rain.md](../../examples/source-texts/weather-rain.md)

> 昨天下午我在圖書館看書的時候，突然下起了大雨。雖然我沒帶傘，但還是決定走路回家。路上人很多，到處都是撐著傘的行人。我全身都淋濕了，回到家才發現鑰匙忘在辦公室了。鄰居看到我的樣子，笑著說：「你怎麼不叫計程車？」我只好苦笑著回答：「我忘了帶錢包。」

### Light

> 昨天下午我在圖書館看書的時候，突然下起了大雨。雖然我沒帶遮，但還是決定行路回屋企。路上人很多，到處都是撐著遮的行人。我全身都淋濕了，回到屋企才發現鎖匙忘在 office 了。鄰居看到我的樣子，笑著說：「你為何不叫的士？」我只好苦笑著回答：「我忘了帶銀包。」

### Medium（預設）

> 琴日下午我在圖書館睇書的時候，突然下起一場大雨。我雖然沒帶遮，但還是決定行路返屋企。條街上好多人，到處都是撐著遮的人。我全身濕晒，返到屋企先發現條鎖匙唔記得在 office。隔籬鄰居見到我這樣，笑著說：「你點解唔 call 的士？」我唯有苦笑答：「Sorry 啊，我唔記得帶銀包。」

### Heavy

> 琴日下午我喺 library 睇緊書嗰陣，突然落咗一場大雨。我雖然冇帶遮，but 都決定行路返屋企。條街人多到爆，到處都係撐住遮嘅人。我全身濕晒，返到屋企先發現條鎖匙唔記得咗喺 office。隔籬阿婆見到我咁 cham，笑住講：「你點解唔 call 的士啊？」我唯有苦笑答：「Sorry 啊，我真係唔記得咗帶個 wallet。」

---

## 範例二：小王子（英文源 → 港式中文）

源文：[little-prince.md](../../examples/source-texts/little-prince.md)

> The little prince lived alone on a tiny planet, no bigger than a house. He had three volcanoes to clean, and a rose that he loved very much. Every morning, he would clean his volcanoes and water his rose. One day, he decided to leave his planet to explore the universe. He was sad to say goodbye, but he knew he had to go.

### Light

> 小王子一個人住在一個很小的星球上，沒有一間屋那麼大。他有三座火山，還有一朵他很愛的玫瑰。每朝早他都會清理火山、灌溉玫瑰。有一天他決定離開星球，去 explore 個宇宙。要 say goodbye 的時候他很難過，但他知道自己一定要走。

### Medium

> 小王子自己一個人住在一粒好細的星球，沒一間屋咁大。他有三座火山，仲有一朵他好愛的玫瑰。每朝早他都會去 clean 啲火山，再 water 朵玫瑰。有一日他決定要離開個星球，去 explore 個 universe。講 goodbye 的時候他好難過，不過他知道自己一定要走。

### Heavy

> 小王子一個人住喺一粒細到爆嘅星球度，連一間屋都唔夠大。佢有三座 volcano，仲有一朵佢勁愛嘅 rose。每朝早佢都會去 clean 啲 volcano，再 water 朵 rose。有一日佢決定要 leave 個星球，去 explore 成個 universe。講 goodbye 嗰陣佢真係好 sad，不過佢知道自己一定要走㗎。

---

## 強度速查

| 強度 | 特徵 | 典型場景 |
|---|---|---|
| **Light** | 港式常用詞（巴士/雪櫃/屋企）＋ 港式音譯（荷里活/梳化/三文治）＋ 少量 code-mixing。保留「是/不/沒/的/了/他」骨架 | 港府公告、商務 email |
| **Medium**（預設） | 傳承詞（食/飲/睇/瞓/行）＋ 選擇性粵字（啲/嘢/點解/唔）＋ 頻繁 code-mixing ＋ 詞序倒置。混合骨架 | Apple Daily、Ming Pao、HK01 專欄 |
| **Heavy** | 粵語虛詞自由替換（係/唔/冇/嘅/咗/佢/呢/嗰）＋ 句末助詞（㗎/啦/囉/喎）＋ 密集 code-mixing | LIHKG、WhatsApp、casual blog |

> **Note**: Heavy 模式已涵蓋完整粵語書面化。日後若新增 `written-cantonese` skill，本 skill 的 Heavy 可能會收窄。詳見 [SKILL.md](../SKILL.md) 的 Important Notes。

完整 checklist 見 [SKILL.md](../SKILL.md)。
