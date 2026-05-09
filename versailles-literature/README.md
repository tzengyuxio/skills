# Versailles-literature — 改寫成凡爾賽文學

把任何文章改寫成凡爾賽文學——表面抱怨、實則炫耀的中文網路文體。

不是「教人炫富」的工具，而是「讓抱怨完全淹沒炫耀」的文體轉換器——
讀完讓人第一秒共情，第二秒才驚覺：「等等，她剛剛說的是 Birkin？」

## 什麼是凡爾賽文學？

「凡爾賽文學」（簡稱「凡學」）是 2020 年在中文社群網路爆紅的
humblebrag（謙虛吹噓）文體。名稱出自日本漫畫《凡爾賽玫瑰》對 18 世紀
法王路易十六時代凡爾賽宮浮華奢靡貴族生活的描繪。

| 時間 | 事件 |
|---|---|
| 2020-05 | 微博博主@小奶球（豆瓣「凡爾賽學研習小組」創辦人）首次定義「凡爾賽文學」三要素，被《南方週末》稱為「凡學」創始人 |
| 2020-11 | 微博博主蒙淇淇77 連續貼文（北京別墅、KITON 高訂西裝、英法雙語保姆）被網友翻出，「凡爾賽文學」「凡爾賽終結者」登上微博熱搜，正式進入大眾視野 |

**三要素**（@小奶球版）：

1. **先抑後揚、明貶暗褒**——用抱怨包裝炫耀
2. **自問自答**——「為什麼會這樣呢？」「我做錯什麼了嗎？」
3. **靈活運用第三人稱**——借他人之口稱讚自己

## 與「直接炫富」的差異

四川師範大學心理學教授游永恆指出：「凡爾賽人炫富⋯⋯通過炫來顯示
『高貴』當然是一條捷徑，但真正的高貴是靠學識、修養和個人能力來
構建的。」心理學上稱此為「過度補償」。

| 維度 | 直接炫富 | 凡爾賽文學 |
|---|---|---|
| 表面 | 直接陳述擁有 | 抱怨某種困擾 |
| 內裡 | 炫耀本身 | 炫耀本身 |
| 弱化詞 | 無 | **必有**（不小心、隨便、明明、又、只是）|
| 收尾 | 結論／斷言 | **反問／佯困惑** |
| 讀者反應 | 即時反感 | **延遲意會**（讀完幾秒才驚覺）|
| 角色自覺 | 自覺炫耀 | **誠摯抱怨**（不可破格） |

`versailles-literature` 鎖定的是凡爾賽特有的**延遲意會**效果——抱怨必須
完全淹沒炫耀，讀者第一秒共情，第二秒才反應過來。

## 一句話靈魂

**抱怨包裝的炫耀**——抱怨完全淹沒炫耀，讀者讀完應該後知後覺：「等等，
她剛才說的是 Birkin？」

## 三段公式（Hard）

凡爾賽必有三段，缺一不成立：

1. **抱怨開端**——純抱怨，不露品牌／價格／地點細節
2. **細節暴擊**——用弱化詞（不小心、隨便、明明）掩護下，塞入具體
   品牌／價格／地點／身份
3. **反問收尾**——「為什麼會這樣呢？」「我也很想低調啊」「真的好煩」

## 預期輸出篇幅

繁體中文社群口語，**200–500 字**（計入標點）：

| 原文長度 | 凡爾賽目標 |
|---|---|
| 短（< 200 字）| 200–350 字 |
| 中（200–800 字）| 250–450 字 |
| 長（800+ 字）| 抽單一主題寫 300–500 字 |

低於 200 字無法承載三段結構的抱怨密度，超過 500 字會稀釋餘韻。

## 適合的源文

- 生活軼事（房產、車、衣著、子女）
- 職場心得（出差、會議、升遷）
- 旅遊／消費紀錄（出國、奢侈品、餐廳）
- 議論／哲思（先抽出可炫資源再包裝，例：「努力的意義」→「老公太
  努力反而不陪我」）

## 不太適合的源文

- 學術論文／純技術文件（可炫資源稀薄）
- 純抒情詩（缺乏可被改寫成抱怨的事件結構）
- 已是炫富文（改寫意義不大；可考慮反向改寫）
- 嚴肅新聞報導（需先「私人化」才能用凡學包裝）

## 安裝

一行安裝：

```bash
git clone --depth 1 https://github.com/tzengyuxio/skills.git /tmp/tz-skills \
  && mkdir -p ~/.claude/skills \
  && cp -r /tmp/tz-skills/versailles-literature ~/.claude/skills/ \
  && rm -rf /tmp/tz-skills
```

或透過 plugin marketplace：

```
/plugin marketplace add tzengyuxio/skills
/plugin install versailles-literature@tzengyuxio-skills
```

手動安裝：

```bash
cp -r versailles-literature ~/.claude/skills/versailles-literature
```

## 使用方式

```
/versailles-literature path/to/article.md
```

也可以直接貼一段文字進來，或剛寫完一份文件後無參數呼叫。

**觸發詞**：`/versailles-literature`、「改寫成凡爾賽」「凡爾賽文學」
「假裝抱怨真炫耀」「蒙淇淇體」「rewrite as Versailles literature」
「humblebrag this」「Versailles flex」

## 運作流程

1. **讀原文** — 載入文字
2. **抽資源** — 列出可炫耀的物質／關係／經歷／身份／容貌
3. **設計困擾包裝** — 為這項資源虛構一個讀者第一秒能共情的困擾
4. **草稿三段** — 抱怨開端 → 細節暴擊 → 反問收尾
5. **檢查弱化詞密度** — 至少 2 個（不小心、隨便、又、明明、只是⋯⋯）
6. **檢查炫耀是否被淹沒** — 第一段不能露品牌；首句要能讓讀者共情
7. **朗讀** — 若聽起來像「直接炫」就回 Step 3 加重抱怨
8. **Checklist 自檢** — 21 條（Hard 15 + Soft 6）
9. **輸出** — 寫入 `<原檔名>_versailles.md`

## 改寫原則（checklist 摘要）

| 類別 | 編號 | 要點 |
|---|---|---|
| Content | C-01~C-05 | 抱怨包裝炫耀（soul）、三段公式齊備、不可直接炫富、不可有自我意識、主題抽象化 |
| Structure | S-01~S-06 | 篇幅 200–500 字、第一段純抱怨、第二段必有細節暴擊、第三段必為反問、餘韻 |
| Voice | V-01~V-05 | 弱化副詞必用、品牌／關係詞必出現、第一人稱社群口語、emoji（選）、自問自答（選）|
| Meta | M-01~M-05 | 不附評論段、角色須誠摯、不可直接炫富、主輸出不附自評表、議論文先抽張力 |

完整 21 項 checklist 與 9 步 workflow 見 [SKILL.md](./SKILL.md)。

## 三條靈魂條款

凡爾賽文學的指紋：

1. **C-01 抱怨包裝的炫耀** — 抱怨完全淹沒炫耀
2. **C-02 三段公式齊備** — 抱怨開端 + 細節暴擊 + 反問收尾
3. **M-02 角色須誠摯** — 氣質是「天真且煩惱」，絕不可破口自承

三者缺一就不是凡爾賽。其餘 18 條 checklist 都在服務這三條。

## 詞彙庫速查

### 弱化副詞（V-01 必用）
不小心、隨便、又、明明、真的好、實在、不過是、只是、剛好、順便

### 品牌／經歷詞庫（V-02 範例）
Hermes、Birkin、Cartier、Chanel、Gucci、Patek、瑪莎拉蒂、私人飛機、
巴黎、米其林、KITON、蘇黎世、紐約路演、別墅、限量配額

### 關係詞庫
老公送的、朋友幫訂的、他總是、上次誰誰誰也是、人家說的、櫃姐說、
祕書安排、閨蜜笑我說

### 反問收尾庫
為什麼會這樣呢？／我也很想低調啊／真的好煩／明明說過很多次了／
他怎麼又這樣？／到底要我怎麼辦才好？／為什麼是我啊⋯⋯

## 示範

完整的 Before / After 對照（含改寫要點標記）請見
[examples/demo.md](./examples/demo.md)：

- **範例一：物質炫耀** — 包堆不下了（Birkin / Cartier / 巴黎）
- **範例二：關係炫耀** — 老公太招搖（瑪莎拉蒂 / 保時捷預購）
- **範例三：經歷炫耀** — 飛太頻繁（蘇黎世合夥人會議 / 紐約路演）
- **範例四：差不多先生 → 凡爾賽** — 把胡適諷刺寓言改寫成婚姻抱怨

## Changelog

### v1 — 2026-05-09

- 初版：21 項 checklist（Hard 15 + Soft 6）、9 步 workflow、三條靈魂
  條款、4 則示範（物質／關係／經歷／差不多先生改寫）
- 設計取材自 2020 年微博@小奶球三要素（先抑後揚／自問自答／第三人稱）
  與蒙淇淇77 範本句式
- 弱化詞庫、品牌庫、關係詞庫、反問收尾庫四件套定型

## 參考資料

- [凡爾賽文學 - 維基百科](https://zh.wikipedia.org/zh-tw/%E5%87%A1%E5%B0%94%E8%B5%9B%E6%96%87%E5%AD%A6)
- [凡尔赛文学 - 百度百科](https://baike.baidu.com/item/%E5%87%A1%E5%B0%94%E8%B5%9B%E6%96%87%E5%AD%A6/54290433)
- [Mu, Y., et al. *What is "Versailles Literature"?: Humblebrags on
  Chinese social networking sites*. ScienceDirect (2021)](https://www.sciencedirect.com/science/article/abs/pii/S0378216621002885)
  — 學術定義與 humblebrag 定位
- [Sixth Tone, *China's Influencer Generation Has Discovered the
  Humblebrag*](https://www.sixthtone.com/news/1006430/chinas-influencer-generation-has-discovered-the-humblebrag)
  — 蒙淇淇77 個案分析
- [Language Log, *"Involution", "working man", and "Versailles
  literature": memes of embitterment*](https://languagelog.ldc.upenn.edu/nll/?p=49709)
  — 社會語言學脈絡
- [鏡週刊《老公買給我的 Gucci 包好醜喔》](https://www.mirrormedia.mg/story/20201125edi042)
  — 中文媒體最早的凡爾賽範例彙整
- [A Day Magazine《男友又買禮物給我，真討厭》](https://www.adaymag.com/2020/11/22/versailles-style-internet-post.html)
  — 心理學「過度補償」分析
- [海基會《凡爾賽文學 不一樣的「炫風」》](https://www.sef.org.tw/article-1-129-12841)
  — 兩岸社會語言比較

## 相關技能

- [koanify](../koanify/) — 改寫為敘事禪宗公案
- [liaozhai-tale](../liaozhai-tale/) — 改寫為聊齋體文言短篇
- [qiongyao-style](../qiongyao-style/) — 改寫為瓊瑤式愛情敘事
- [jinyong-style](../jinyong-style/) — 改寫為中期金庸武俠
- [gulong-style](../gulong-style/) — 改寫為中後期古龍武俠
- [shakespeare-style](../shakespeare-style/) — 改寫為莎士比亞中譯體
