# Skills — 中文語體轉換工具集

針對**中文語體、風格、地域變體、歷時風貌、文學體裁**的系統性轉換技能集，為 [Claude Code](https://docs.anthropic.com/en/docs/claude-code) 及相容 AI 編程助手打造。

目前收錄 43 個 skill，分為 10 個分類：

| 分類 | skill 數 | 範圍 |
|---|---|---|
| AI 寫作風格處理 | 1 | humanize（去 AI 痕跡） |
| 翻譯腔處理 | 2 | dewesternise / westernise |
| 中英語言混搭 | 4 | chinglish / singlish / hanjify / jingjing-style |
| 地域中文變體 | 9 | taiwan / hongkong / singapore / mainland / dongbei / shanghainese / sichuan / written-hokkien / written-cantonese |
| 應用文類 | 2 | prc-bureaucratese / roc-bureaucratese-classic |
| 文言文改寫 | 4 | wenyan-xianqin / hanwei / guwen / huaben |
| 文學體裁改寫 | 12 | koanify / liaozhai-tale / qiongyao-style / gulong-style / jinyong-style / shakespeare-style / eileen-chang-style / yu-guangzhong-style / bagu-essay / hemingway-style / lu-xun-style / sherlock-holmes-style |
| 古典詩詞 | 2 | tang-poem-style / song-ci-style |
| 詮釋型改寫（lens） | 2 | psychoanalytic-lens / postmodern-lens |
| 網路文體 | 4 | feihua-literature / zhiyin-style / versailles-literature / concrete-42 |

> [English version](./README_EN.md)

## 特色

- **強度光譜可控**：歐化處理與地域變體類 skill 提供**輕／中／重**三段強度，依目標 register 選擇（其餘類別為單一目標輸出，不分強度）
- **系統化 checklist**：每個 skill 都有 20-30 項明確規則，每項標記軟硬程度與（適用時）啟用強度，可重現、可追溯
- **語言學嚴謹**：明確劃定各 skill 的語言學範疇、引用相關研究（邵敬敏、Jerry Norman、胡適等）、以真實語料為範本、**排除 caricature**——把語言變體當真實系統對待，不當嘲諷對象
- **逆操作對偶、可組合**：兩組對偶 skill：`dewesternise` ↔ `westernise`、`gulong-style` ↔ `jinyong-style`（短句留白派 vs 章回招式派）；skills 可串接使用（如 `dewesternise` → `taiwan-mandarin`）
- **公開示範與本地實驗分離**：各 skill 的 [`examples/`](./examples/) 收錄乾淨展示，共用 [`examples/source-texts/`](./examples/source-texts/) 源文庫讓各 skill 可橫向比較

## 可用技能

### AI 寫作風格處理

| 技能 | 功能 | 範例 |
|------|------|------|
| [humanize](./humanize/) | 去除 AI 生成文字的寫作痕跡（26 項 checklist，支援中英文） | [demo](./humanize/examples/demo.md) |

### 翻譯腔處理

針對中文「歐化」（翻譯腔）現象的風格轉換工具，各附 25 項 checklist，互為逆操作。

| 技能 | 功能 | 範例 |
|------|------|------|
| [dewesternise](./dewesternise/) | 去除中文的歐化寫法（被動句、抽象主語、長前飾語等） | [demo](./dewesternise/examples/demo.md) |
| [westernise](./westernise/) | 刻意加入翻譯腔（支援輕／中／重三段強度） | [demo](./westernise/examples/demo.md) |

### 中英語言混搭

英語變體與書寫系統轉換工具——將文字轉為各種受華語影響的英語風格或混合書寫系統。

| 技能 | 功能 | 範例 |
|------|------|------|
| [chinglish](./chinglish/) | 將中文或英文轉為中式英語（Chinglish）——重現母語干擾下的系統性變異 | [demo](./chinglish/examples/demo.md) |
| [singlish](./singlish/) | 將任何文字轉為新加坡式英語（Singlish）——融合閩南語、馬來語的克里奧爾語言 | [demo](./singlish/examples/demo.md) |
| [hanjify](./hanjify/) | 將英文轉換為漢字化英語——漢字承載語意，保留英語文法（送假名風格形態學） | [demo](./hanjify/examples/demo.md) |
| [jingjing-style](./jingjing-style/) | 將文字轉為晶晶體——中文基底夾不必要的簡單英文字（amazing/busy/hot/fashion），炫耀感從「明明可中譯卻用英文」中產生；2016 起的台灣媒體名媛口語現象；輕／中／重三段強度 | [demo](./jingjing-style/examples/demo.md) |

### 地域中文變體

將文字轉為不同華語社群的在地口語/書面變體，各附 checklist 與輕／中／重三段強度。

| 技能 | 功能 | 範例 |
|------|------|------|
| [taiwan-mandarin](./taiwan-mandarin/) | 將文字轉為台灣國語——融合台語/日語借詞、擬音字（偶/粉/素/降）、注音文、語尾助詞（啦/喔/齁/耶） | [demo](./taiwan-mandarin/examples/demo.md) |
| [hongkong-chinese](./hongkong-chinese/) | 將文字轉為港式中文——港式詞彙（巴士/的士/雪櫃）、港式音譯（荷里活/梳化/三文治）、中英夾雜、詞序倒置；Heavy 模式可涵蓋完整粵語書面化（係/唔/嘅/咗/佢/呢/嗰） | [demo](./hongkong-chinese/examples/demo.md) |
| [singapore-mandarin](./singapore-mandarin/) | 將文字轉為新加坡華語——SG 行政生活詞（組屋/德士/樂齡/客工）、閩南語借詞（幾時/不懂/做工/怕輸）、馬來語借詞（甘榜/巴剎/atas/bodoh）、先後置句式、千-單位數字；與 singlish 共構 SG 雙胞胎 | [demo](./singapore-mandarin/examples/demo.md) |
| [dongbei-mandarin](./dongbei-mandarin/) | 將文字轉為東北話——東北官話三省（黑吉遼）口語節奏，賊／嘎哈／咋整／老鐵／妥妥的標誌詞，趙本山＋二人轉＋抖音老鐵語料；輕／中／重三段強度 | [demo](./dongbei-mandarin/examples/demo.md) |
| [shanghainese](./shanghainese/) | 將文字轉為上海話／吳語——人稱替換（儂／阿拉／伊）＋否定詞（弗／勿／覅）＋句末助詞（呃／嘞／伐）＋海派標誌詞（結棍／霞氣／嗲／戇／淘漿糊）；金宇澄《繁花》風格；輕／中／重三段強度 | [demo](./shanghainese/examples/demo.md) |
| [sichuan-mandarin](./sichuan-mandarin/) | 將文字轉為四川話／川渝風格——西南官話成渝片，川渝江湖氣＋兒化重＋句末助詞密集（嘛／噻／嘞／哈），標誌詞巴適／安逸／莫得／搞快點／龜兒；《讓子彈飛》《火鍋英雄》風格；輕／中／重三段強度 | [demo](./sichuan-mandarin/examples/demo.md) |
| [written-hokkien](./written-hokkien/) | 將文字轉為台語／閩南語書面化——句法走台語（不是中文翻譯），本字使用（阮／咱／怹／ê／beh／攏／毋／莫）；兩段強度：Light 純漢字（教育部 700 字）／ Heavy 漢羅混寫（本字漢字＋台羅）；鄭清文／賴和／陳明仁文學傳統 | [demo](./written-hokkien/examples/demo.md) |
| [mainland-mandarin](./mainland-mandarin/) | 將文字轉為中國大陸普通話日常／媒體文體——大陸用法詞彙（視頻／質量／出租車／公交／軟件）＋網路用語（內卷／躺平／yyds／破防／絕絕子／家人們）＋微博／抖音／B 站／小紅書文體；與 prc-bureaucratese（公文）區隔；輕／中／重三段強度 | [demo](./mainland-mandarin/examples/demo.md) |
| [written-cantonese](./written-cantonese/) | 將文字轉為完整粵語書面語（syntax 也粵語化）——核心虛詞（係／唔／嘅／咗／佢／喺）＋句末助詞（喎／啦／㗎／咩）＋粵語語序（副詞後置／動補後置／雙賓語）；TVB／Apple Daily／LIHKG 連登；輕／中／重三段強度 | [demo](./written-cantonese/examples/demo.md) |

### 應用文類

中文特定應用文體的制度化風格轉換。目前收錄兩種公文體，預留擴充給其他應用文類型（書信、啟事、契約、會議紀錄、自傳等）。

| 技能 | 功能 | 範例 |
|------|------|------|
| [prc-bureaucratese](./prc-bureaucratese/) | 將文字轉為中共黨政公文體——高頻動詞（落實/加強/推進/深化）、副詞堆疊（紮實推進/深入貫徹/全面落實）、四字格對偶（不忘初心、牢記使命）、數字化政治套語（四個全面/五位一體）、新時代意識形態詞彙 | [demo](./prc-bureaucratese/examples/demo.md) |
| [roc-bureaucratese-classic](./roc-bureaucratese-classic/) | 將文字轉為 1960-80 年代中華民國公文體——文言單字（之/於/以/係/為/俾/爰）、文言連接詞（茲/惟/嗣/俟/頃）、階層敬語（鈞/貴/本/職/台端）、程序套語（查照/鑒核/核備/奉悉）、主旨-說明-辦法格式 | [demo](./roc-bureaucratese-classic/examples/demo.md) |

### 文言文改寫

將現代中文改寫為不同時期的文言風格，各附 20-22 項 checklist。

| 技能 | 風格 | 代表作品 | 範例 |
|------|------|---------|------|
| [wenyan-xianqin](./wenyan-xianqin/) | 先秦諸子體 | 論語、莊子、韓非子 | [demo](./wenyan-xianqin/examples/demo.md) |
| [wenyan-hanwei](./wenyan-hanwei/) | 漢魏史傳體 | 史記、漢書、三國志 | [demo](./wenyan-hanwei/examples/demo.md) |
| [wenyan-guwen](./wenyan-guwen/) | 唐宋古文體 | 韓愈、蘇軾、歐陽修 | [demo](./wenyan-guwen/examples/demo.md) |
| [wenyan-huaben](./wenyan-huaben/) | 話本小說體 | 水滸傳、三國演義、紅樓夢 | [demo](./wenyan-huaben/examples/demo.md) |

### 文學體裁改寫

將文章改寫為特定文學體裁——不只是文體微調，而是連敘事結構、角色設定、留白手法都重新組織。預留擴充給其他文學體裁（寓言、童話、神話、推理、奇幻等）。

| 技能 | 功能 | 範例 |
|------|------|------|
| [koanify](./koanify/) | 改寫為敘事禪宗公案——白隱「是這樣嗎?」流派，100–400 字白話偏雅，留白八式擇一 | [demo](./koanify/examples/demo.md) |
| [liaozhai-tale](./liaozhai-tale/) | 改寫為聊齋體文言短篇——蒲松齡流派，200–800 字純文言，必有「異化」元素（狐／鬼／妖／精等） | [demo](./liaozhai-tale/examples/demo.md) |
| [qiongyao-style](./qiongyao-style/) | 改寫為中期瓊瑤體愛情敘事——《在水一方》《一簾幽夢》流派，300–800 字白話文藝，必有愛情軸與阻礙，痛感收尾 | [demo](./qiongyao-style/examples/demo.md) |
| [gulong-style](./gulong-style/) | 改寫為中後期古龍武俠——1969《多情劍客無情劍》後成熟期，200–600 字極短句節奏，警句嵌入，必有對比張力，不寫武打過程 | [demo](./gulong-style/examples/demo.md) |
| [jinyong-style](./jinyong-style/) | 改寫為中期黃金期金庸武俠——1957–1969 五大代表作（射鵰/神鵰/倚天/天龍/笑傲），400–1200 字章回式長句，必有招式詳寫＋詩詞嵌入＋歷史錨定 | [demo](./jinyong-style/examples/demo.md) |
| [shakespeare-style](./shakespeare-style/) | 改寫為朱生豪式中譯莎劇悲劇腔——四大悲劇流派，300–1000 字半文白戲劇腔，譬喻密度＋戲劇性情感＋獨白(≥30%) | [demo](./shakespeare-style/examples/demo.md) |
| [eileen-chang-style](./eileen-chang-style/) | 改寫為張愛玲體——蒼涼基調必現，月光／鏡子／絲綢／舊上海公寓意象群，女性凝視＋細節暴力＋反高潮收尾，情感壓住不爆破 | [demo](./eileen-chang-style/examples/demo.md) |
| [yu-guangzhong-style](./yu-guangzhong-style/) | 改寫為余光中體散文——文白交織必現，長句鋪排＋真排比＋古典詩詞化用，地理錨點以余實際生平足跡為準（重慶／廈門／沙田／西子灣） | [demo](./yu-guangzhong-style/examples/demo.md) |
| [bagu-essay](./bagu-essay/) | 改寫為明清八股文——破題承題起講入手＋起股中股後股束股八段齊備，四股兩兩對仗，代聖人立言禁第一人稱，附王鏊〈百姓足君孰與不足〉參照樣本 | [demo](./bagu-essay/examples/demo.md) |
| [hemingway-style](./hemingway-style/) | 改寫為海明威體中譯版——冰山理論七分情緒水下，短句＋動詞主導＋具體名詞，重複錨定（同詞／同句構／同動作），歐化翻譯腔為 feature 非違規 | [demo](./hemingway-style/examples/demo.md) |
| [lu-xun-style](./lu-xun-style/) | 改寫為魯迅體——冷峻反諷的早期白話，文白夾雜＋標誌虛詞密集（然而／便／罷了／未免／實在／想來）＋第一人稱「我」＋反諷距離（不嘲弄不認同）；定位為文體致敬而非立場模仿，反諷對象限抽象普世（國民性／看客／苟且） | [demo](./lu-xun-style/examples/demo.md) |
| [sherlock-holmes-style](./sherlock-holmes-style/) | 改寫為朱生豪式中譯維多利亞偵探小說腔——Conan Doyle《福爾摩斯探案》中譯本流派，第一人稱華生回憶體＋福爾摩斯演繹獨白（我親愛的華生）＋案件三幕（委託登門→現場勘察→演繹揭曉）＋維多利亞物件密度（煤氣燈／懷錶／菸斗／馬車／哈德森太太／蘇格蘭場）；世界觀層必走西洋通名禁中華具體位移；中譯翻譯腔為 feature；輕／中／重三段強度 | [demo](./sherlock-holmes-style/examples/demo.md) |

### 古典詩詞

將文章壓縮、淘洗、煉成中國古典格律詩詞。鎖定平仄、押韻、對仗等硬格律，意境靠古典意象搬移承載。預留擴充給其他韻文體裁（宋詞、樂府、歌行、元曲等）。

| 技能 | 功能 | 範例 |
|------|------|------|
| [tang-poem-style](./tang-poem-style/) | 改寫為唐詩——五言絕句／七言絕句／五言律詩／七言律詩四種規格擇一，平水韻一韻到底＋平仄循譜（含平起仄起兩式）＋律詩中二聯對仗（頷聯／頸聯詞性結構平仄三層對）；古典意象搬移（電車→車馬／鑰匙→玉鎖）；起承轉合＋末句不直白說教；六首唐詩參照樣本（王維／李白／杜牧／李商隱／杜甫×2） | [demo](./tang-poem-style/examples/demo.md) |
| [song-ci-style](./song-ci-style/) | 改寫為宋詞——五個經典詞牌擇一（水調歌頭 95 字／念奴嬌 100 字／虞美人 56 字／如夢令 33 字／西江月 50 字），字數＋句長序列＋押韻位置＋平仄譜＋平仄韻交替類型完全合譜；豪放派 vs 婉約派擇一不可混（[豪放派]／[婉約派] 標籤必出）；現代詞彙零違規（電腦／咖啡／捷運轉古典等價物）；五首參照樣本（蘇軾×2／李煜／李清照／辛棄疾） | [demo](./song-ci-style/examples/demo.md) |

### 詮釋型改寫（lens）

不改變語言表面，而是改變詮釋框架——事件不變，意義重組。改寫文章內部對動機與意義的敘述，讓敘事本身用該理論的眼光看待自己。

| 技能 | 功能 | 範例 |
|------|------|------|
| [psychoanalytic-lens](./psychoanalytic-lens/) | 以精神分析（Freud／Lacan）重寫敘事——保留事件，改寫主敘述為其象徵性根源；流派可選不可混（[F]/[L] 標註）；核心三條款：事件保留／概念自然發生／替代敘述義務 | [demo](./psychoanalytic-lens/examples/demo.md) |
| [postmodern-lens](./postmodern-lens/) | 以後現代理論（Lyotard／Derrida／Foucault／Baudrillard／Jameson／Barthes／Kristeva）重寫敘事——元敘事懷疑必現（敘述者插話質疑、競爭版本、把「應該怎麼講」寫進敘述）；流派可組（[D]+[B]、[F]+[J]、[L]+[Bd]）不可全堆；不寫「德希達會說」式 cite 句 | [demo](./postmodern-lens/examples/demo.md) |

### 網路文體

近年由社群媒體放大的次文化／流行文體，含同義反覆、煽情標題、抱怨式炫耀、偽專業胡言亂語等。每個 skill 將梗的句法與套路系統化為 checklist。

| 技能 | 功能 | 範例 |
|------|------|------|
| [feihua-literature](./feihua-literature/) | 改寫為廢話文學——零信息密度，三大公式（同義替換／首尾矛盾／問答轉換）至少二發；魯迅〈秋夜〉「一棵是棗樹另一棵也是棗樹」是文學史錨點；2021 微博抖音爆紅 | [demo](./feihua-literature/examples/demo.md) |
| [zhiyin-style](./zhiyin-style/) | 改寫為知音體——煽情標題（≥10 字含三疊感嘆）+ 三段式情感悲劇（命運開端／苦難中段／升華收尾）+ 淚血情命義字眼密度；《知音》雜誌 1985 起的中國雜誌煽情敘事體現象 | [demo](./zhiyin-style/examples/demo.md) |
| [versailles-literature](./versailles-literature/) | 改寫為凡爾賽文學——抱怨包裝的炫耀（先抑後揚／自問自答／第三人稱借讚），抱怨完全淹沒炫耀；2020 微博@小奶球+蒙淇淇 77 引爆；學術定位為中文社群網站 humblebrag | [demo](./versailles-literature/examples/demo.md) |
| [concrete-42](./concrete-42/) | 改寫為「義大利麵就應該拌 42 號混凝土」體——偽專業話術＋跨領域名詞拼貼＋邏輯不通卻一本正經；諷刺答非所問／術語堆砌／模糊規避；卧龍鳳雛 2024 起源 | [demo](./concrete-42/examples/demo.md) |

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
