---
name: dongbei-mandarin
description: >
  Transform text into Dongbei Mandarin （東北話） — the Northeast Chinese variant of
  Mandarin spoken across Heilongjiang, Jilin, and Liaoning, shaped by long contact
  with Manchu, Mongolian, Russian, and a strong oral-performance tradition （二人轉、
  小品、《鄉村愛情》). Features the all-purpose verb 整， the intensifier 賊，
  signature lexicon （嘎哈/咋整/老鐵/妥妥的/杠杠的/必須的/可勁兒/瞅）, 老 X / 小 X
  prefixes, moderate 兒化， sentence-final particles （唄/咧/哈/嘎/嗯哪）, short
  punchy clauses, rhetorical questions, and onomatopoeia. Three intensity levels:
  Light (a few markers on a Mandarin backbone), Medium (clearly Dongbei-flavored
  conversational text), Heavy (《鄉村愛情》-style oral-performance register).
  Useful for creative writing, cultural appreciation, language education, or humor.
  Triggers on "/dongbei-mandarin", "寫成東北話", "東北話", "東北腔", "大碴子味",
  "二人轉腔", "趙本山體", "make it dongbei", "Northeast Chinese style", "賊 X",
  "嘎哈", "咋整", "老鐵".
license: PolyForm Noncommercial 1.0.0
argument-hint: [file-path]
allowed-tools: Read, Write, Edit, Glob
---

# Dongbei Mandarin — 東北話

Transform text into Dongbei Mandarin （東北話） — a living variety of 北方官話 spoken
across the Northeast （黑龍江 / 吉林 / 遼寧 三省，及內蒙東部部分地區）. The result
should read like a Heilongjiang neighbor over a 燒烤 table, a 二人轉 stage line,
or a《鄉村愛情》scene — warm, direct, rhythm-driven, unmistakably 東北.

東北話 is **not** "rough Mandarin" or a punchline. It is a 官話次方言，with its own
phonology （兒化、捲舌變平舌、入聲歸上聲）, lexicon （滿、蒙、俄借詞層）, and a
celebrated **口語表演傳統** （二人轉、小品、短視頻直播）. This skill targets the
**written representation** of that orality — the way Dongbei voice surfaces on
screen, in subtitles, in social media captions, and in transcribed scripts.

## Arguments

- `$0` — (Optional) Path to a markdown or text file. If omitted, ask for inline
  text or find the most recent text in conversation context.

## Step 1: Load the Text

- If `$0` is provided, read the file.
- If no argument, find the most recent text in the conversation, or ask the user.
- The input can be **Standard Mandarin** (rewrite as Dongbei), **any language**
  (translate to Dongbei Mandarin), or **English** (translate to Dongbei Mandarin).

## Step 2: Apply Dongbei Mandarin Patterns

Apply the rules below systematically. Goal: every paragraph carries multiple
Dongbei markers — at least one of {整，賊，老 X, 嘎哈/咋整，唄/哈/嗯哪} per
2-3 sentences. Not every rule applies to every sentence — pick what fits.

東北話 sits on a continuum from a Mandarin backbone with one or two flavor words
to full《鄉村愛情》-style oral register. This skill targets that full range and
deliberately **excludes caricature** — no "drunk / brawler / uneducated" framing.

---

### Grammar Patterns（語法模式）

#### G1. 「整」字 — 萬用動詞 [Hard, Light+]

「整」(zhěng) substitutes for almost any action verb — 做、弄、辦、搞、吃、喝、
玩、修、買、安排. The signature feature of Dongbei Mandarin syntax.

> **Standard:** 我們去吃點東西吧。
>
> **Dongbei:** 咱整點吃的去唄。

> **Standard:** 這事怎麼辦？
>
> **Dongbei:** 這事兒咋整啊？

> **Standard:** 把這個問題解決一下。
>
> **Dongbei:** 把這個事兒整明白了。

> **Standard:** 放點音樂。
>
> **Dongbei:** 整點兒音樂。

#### G2. 「賊」+ 形容詞 / 副詞 — 程度強化 [Hard, Light+]

「賊」(zéi) functions as the most iconic Dongbei intensifier — equivalent to 很 / 非
常 / 超. Slot it freely before adjectives, stative verbs, and some action verbs.

> **Standard:** 今天非常冷。
>
> **Dongbei:** 今兒個賊冷。

> **Standard:** 這菜很好吃。
>
> **Dongbei:** 這菜賊香。

> **Standard:** 他跑得很快。
>
> **Dongbei:** 他跑得賊快。

#### G3. 「老 X」/「小 X」前綴 — 人稱與稱呼 [Hard, Light+]

「老」+ 一字（姓 / 排行 / 形容）→ 親近稱呼；「小」+ 一字 → 對年幼者或晚輩。
不限熟人——東北話對陌生人也常用「老哥 / 老妹 / 老弟 / 大姐」開場。

| 稱呼 | 場合 |
|---|---|
| 老鐵 | 鐵哥們、好朋友（直播時代外溢全國） |
| 老哥 / 老弟 / 老妹 | 對同輩或略長者；陌生人也可用 |
| 大兄弟 / 大姐 | 對陌生男女的親切招呼 |
| 老娘們兒 / 老爺們兒 | 中年女 / 中年男（中性，視語境可帶玩笑） |
| 小屁孩兒 / 小崽子 | 對小孩（親暱，非貶） |
| 老 + 姓（老李 / 老王） | 同輩熟人 |

> **Standard:** 各位朋友好。
>
> **Dongbei:** 老鐵們好啊。

#### G4. 「給我」/「給你」+ V — 語氣框架 [Hard, Medium+]

「給我」加強語氣（命令 / 抱怨 / 自述被影響），「給你」用於敘事中的「結果竟然」。

> **強化命令：** 你給我老實點兒。
>
> **抱怨：** 可給我整鬱悶了。 / 可給我整笑了。
>
> **敘事結果：** 他給你來這麼一手，誰受得了？

#### G5. 反問與雙重否定 — 節奏修辭 [Hard, Light+]

東北話常用反問代替陳述，加強情感濃度；雙重否定也常見。

> **Standard:** 我也沒辦法。
>
> **Dongbei:** 我能咋整啊？

> **Standard:** 當然要去。
>
> **Dongbei:** 那咋能不去呢？

> **Standard:** 真的就是這樣。
>
> **Dongbei:** 可不就這麼回事兒嗎。

#### G6. 動詞重疊 + 兒化 [Soft, Medium+]

「V V 兒」式重疊用得頻繁，比北京話更自由：嘮嘮兒、嘚嘚兒、整整兒、瞅瞅兒、
嘎嘎兒。

> 咱倆嘮嘮兒。
>
> 他嘚嘚兒半天，啥重點都沒有。
>
> 你瞅瞅兒這事兒整的。

#### G7. 「可」+ V/A 的強調用法 [Hard, Medium+]

「可」（kě）作副詞，強調超出預期或感慨——不同於台灣國語的「可」。

> 可給我整笑了！  *（笑到不行）*
>
> 那玩意兒可不是一般地貴。
>
> 他可有意思了。

#### G8. 句首「咱（們）」與聽話人共謀感 [Soft, Light+]

東北話偏愛「咱 / 咱倆 / 咱大伙兒」開句，把聽話人拉進同一陣線。比「我們」更
親近、更有共謀感。

> **Standard:** 我們先吃飯。
>
> **Dongbei:** 咱先整點兒飯。

> **Standard:** 我們別說了。
>
> **Dongbei:** 咱倆別嘚嘚了。

---

### Vocabulary Patterns（詞彙模式）

#### V1. 標誌動詞與動詞短語 [Hard, Light+]

| 詞 | 普通話 | 備註 |
|---|---|---|
| 整 | 做 / 弄 / 辦 / 搞 | 萬用，見 G1 |
| 嘎哈 | 幹啥（你嘎哈呢？= 你做啥？） | gá-ha, 由「幹啥」訛變 |
| 咋整 | 怎麼辦 | 標誌句式 |
| 咋滴 / 咋的 | 怎麼了 / 怎麼著 | 「你想咋滴？」|
| 瞅 | 看 | 「你瞅啥？」「瞅一眼」 |
| 嘮（嗑兒） | 聊（天） | 「咱嘮嘮兒」 |
| 嘚嘚 | 嘮叨、囉嗦 | 「別嘚嘚了」 |
| 劃拉 | 收拾 / 隨便扒 | 「劃拉劃拉」 |
| 摳搜 | 小氣 | 滿語借詞 |
| 咋呼 | 大聲嚷嚷、虛張聲勢 | 滿語借詞 |
| 倒騰 | 反覆挪動 / 做小買賣 | 「倒騰來倒騰去」 |
| 撒丫子 | 跑、開溜 | 「撒丫子就跑」 |
| 削 | 揍 | 「削他一頓」 |
| 扯犢子 | 胡扯、瞎說 | 較粗，可玩笑用 |

#### V2. 標誌形容詞與程度詞 [Hard, Light+]

| 詞 | 意思 |
|---|---|
| 賊（X）| 很、超、非常（見 G2）|
| 老（X）| 強烈程度（老遠、老多了、老厲害了）|
| 可（X）| 強調（見 G7）|
| 忒（tuī）| 太（忒貴 / 忒能）|
| 杠杠的 | 硬氣、頂呱呱、品質好 |
| 妥妥的 | 穩了、絕對沒問題 |
| 必須的 | 那當然、肯定的 |
| 嘎嘎（X）| 程度極高（嘎嘎冷、嘎嘎好吃）|
| 埋汰 | 髒；引申為「貶損人」 |
| 寒磣（hán-chen）| 醜陋 / 丟臉 |
| 敞亮 | 爽快、不藏心眼 |
| 板正 | 整齊、得體 |
| 嘎不溜脆 | 利落、爽快 |
| 利索 | 利落 |
| 邪乎 | 誇張、不可思議 |

#### V3. 滿 / 蒙 / 俄 借詞層 [Hard, Medium+]

東北話的底層接觸詞——文化上不可省略，也是語言學認證 Dongbei 的硬指標。

| 借詞 | 意思 | 來源 |
|---|---|---|
| 嘎拉哈 | 羊 / 豬距骨遊戲（玩具） | 滿語 |
| 嘞嘞（lē-lē）| 嘮叨 | 滿語 |
| 摳搜 | 小氣 | 滿語 |
| 咋呼 | 大聲嚷嚷 | 滿語 |
| 哈喇（味兒）| 油耗味 | 滿語 |
| 列巴 | 麵包 | 俄語 хлеб |
| 布拉吉 | 連衣裙 | 俄語 платье |
| 馬神 | 機器 | 俄語 машина |
| 笆籬子 | 監獄 | 俄語 полиция |
| 喇忽 | 馬虎、粗心 | 滿語 |

#### V4. 名詞與生活文化詞 [Hard, Light+]

| 詞 | 普通話 |
|---|---|
| 屯子 | 村莊 |
| 疙瘩 | 地方（「那旮（gā）旯（lá）」= 那地方）|
| 旮旯 | 角落、偏僻處 |
| 馬路牙子 | 馬路與人行道間的條石 |
| 大碴子粥 | 玉米碴子粥（東北主食代名詞）|
| 殺豬菜 | 東北殺年豬的傳統菜 |
| 小燒烤 | 街邊燒烤 |
| 大棉襖 | 厚棉衣 |
| 澡堂子 | 公共浴室 |
| 炕 | 北方睡用磚砌床 |
| 大喇叭 | 高音喇叭 / 多嘴的人 |
| 老嘎達 | 家中最小的（滿語底層） |
| 大耳瓜子 | 巴掌（「給你一大耳瓜子」） |

#### V5. 口頭禪與感嘆 [Hard, Light+]

| 詞 | 場合 |
|---|---|
| 妥了 / 妥妥的 | OK、搞定 |
| 必須的 | 那是當然 |
| 杠杠的 | 沒問題、品質好 |
| 那可不（咋的）| 那當然 / 可不是嘛 |
| 嗯哪 | 是啊、對（標誌應答） |
| 可勁兒（X）| 拚命地（可勁兒造、可勁兒整） |
| 我尋思（著）| 我尋思／我心想 |
| 老鐵沒毛病 | 兄弟沒問題（直播流行語） |
| 整挺好 | 弄得挺好 / 很不錯 |
| 你瞅啥 | 你看啥（招呼或挑釁，看語境） |
| 哎媽呀 / 哎呀媽呀 | 驚嘆 |
| 我滴媽呀 / 我的個天 | 驚呼 |
| 完犢子 | 完蛋了 |
| 整景 / 整景兒 | 故弄玄虛、擺譜 |

#### V6. 兒化 — 中等密度 [Hard, Medium+]

東北話兒化頻率高於普通話、低於老北京話。**選擇性**加在名詞、動詞、副詞末。
過度兒化會偏向北京話而非東北話。

**典型兒化詞：** 事兒、活兒、玩意兒、地方兒、今兒個、明兒、晚兒、小燒烤兒、
慢慢兒、好好兒、嘎嘎兒、嘮嗑兒、瞅一眼兒、整事兒。

**不兒化的詞：** 太陽、學校、人民、政府等正式詞與雙音節抽象名詞。

**強度配置：**
- Light：每 4-6 句一個兒化
- Medium：每 2-3 句一個
- Heavy：自由使用，押節奏

---

### Structure Patterns（結構模式）

#### S1. 句末助詞 [Hard, Light+]

東北話句末助詞與北京話部分重疊，但偏好不同。**一句通常一個**助詞，重複堆疊
非典型。

| 助詞 | 功能 |
|---|---|
| 唄 | 緩和建議、無奈接受（「行了唄」「就這樣唄」）|
| 哈 | 親近 / 確認（「明兒見哈」「行不行哈？」）|
| 啊 | 強化 / 開場（「咋整啊」「走啊」）|
| 嘎 | 招呼 / 確認（吉林、黑龍江偏多）|
| 嗯哪 | 應答（= 是啊；見 V5）|
| 咧 | 撒嬌 / 強調（「咋了咧」較少見，偏東部）|
| 呢 | 進行（「他幹啥呢？」）|
| 嗎 | 反問（「能不去嗎？」）|

#### S2. 短句 + 強烈節奏 [Hard, Medium+]

東北話偏好短句與斷裂節奏，不堆長修飾。**每段平均句長 8-14 字**，比書面語短。
高情緒處用「3 字 + 4 字 + 5 字」的階梯。

> **書面：** 這件事情其實沒有想像中那麼困難。
>
> **東北：** 這事兒？沒那麼難。整就完了。

#### S3. 反問與感嘆連珠 [Hard, Medium+]

連續用反問或感嘆，把語氣推上去。

> 你說我容易嗎我？這日子還能不能過了？我招誰惹誰了我？

#### S4. 擬聲詞 [Soft, Medium+]

東北話擬聲詞密集，配合動作給讀者畫面感。

| 擬聲 | 場景 |
|---|---|
| 吭哧吭哧 | 費力、悶頭做 |
| 嘎吱嘎吱 | 雪地、冰面 |
| 咣噹 | 重物落地 |
| 撲棱 | 翅膀拍動、衣服抖動 |
| 嘩啦嘩啦 | 雨、水流 |
| 咯吱咯吱 | 牙齒咬硬物 |
| 噗嗤 | 笑出聲 |
| 嘩啦一聲 | 突發 |

#### S5. 開場與接續詞 [Hard, Light+]

| 詞 | 功能 |
|---|---|
| 我跟你說 | 開場拉注意 |
| 你還別說 | 引出意外觀察 |
| 你說 X 不 X | 反問引共鳴（「你說氣人不氣人」）|
| 那啥 / 那個啥 | 卡詞填空（口語停頓）|
| 反正吧 | 收束、總結 |
| 完了（後）| 然後（敘事接續） |
| 可勁兒（地）| 強調動作幅度 |

#### S6. 標點 — 短句與感嘆密集 [Soft, Medium+]

東北話書寫常用：
- 多重感嘆號「！！」表激動
- 短破折號「——」承接補語
- 問號連用「？？」表錯愕
- 短句之間多用逗號 / 句號斷開，不寫長複句

---

## Step 3: Produce Dongbei Mandarin Output

Apply the checklist to transform the entire text. Aim for a natural, consistent
Dongbei voice at the chosen intensity.

### Intensity Levels

Each rule is tagged with its minimum intensity (e.g., `[Hard, Light+]` = active
from Light up; `[Soft, Heavy]` = mainly Heavy).

| Level | Active Rules | Effect |
|---|---|---|
| **Light** | G1-G3, G5, G8, V1 （核心動詞）, V2 （賊/老/杠杠/妥妥）, V5 （基本口頭禪）, V6 （稀疏兒化）, S1 （唄/哈/啊）, S5 （開場詞）. 每 5-6 句 1-2 處標誌詞。 | 普通東北人發朋友圈、平常聊天。語法骨架仍是普通話，但味道明顯。 |
| **Medium** (default) | Light + G4, G6-G7, V1 （擴展）, V3 （滿俄借詞）, V4 （生活詞）, V5 （完整口頭禪）, V6 （中度兒化）, S2-S5 全用. 每 2-3 句 1 處標誌詞。 | 抖音短視頻字幕、東北博主部落格、二人轉中段。明顯東北腔。|
| **Heavy** | All rules including dense V3 borrowings, S4 onomatopoeia, S6 punctuation, V5 colloquial peaks. 每句 1-2 處標誌詞 + 句末助詞密集。 |《鄉村愛情》劇本級、二人轉舞台對白、直播間即興口語。 |

If the user doesn't specify, use **Medium**.

### Input-Specific Handling

**Standard Mandarin input → Dongbei Mandarin:**
1. Replace generic action verbs with 整 where natural (G1).
2. Promote 很 / 非常 to 賊 (G2). Add 老 X / 嘎嘎 X intensifiers per intensity.
3. Swap human references for 老 X / 小 X / 大兄弟 / 老鐵 frame (G3).
4. Inject 嘎哈 / 咋整 / 瞅 / 嘮 / 嘚嘚 etc. where action verbs sit (V1).
5. Add sentence-final particles (S1) — 唄 for suggestions, 哈 for confirmations,
   啊 for emphasis. One per sentence; don't stack.
6. Break long sentences into shorter Dongbei rhythm (S2).
7. At Medium+, add 滿/俄 borrowings (V3), reduplicated verbs with 兒化 (G6),
   onomatopoeia (S4), opening phrases (S5).
8. At Heavy, push to oral-performance density — short clauses, rhetorical
   chains (S3), 完犢子 / 整挺好 / 嘎嘎 X type colloquial peaks.

**Non-Mandarin input → Dongbei Mandarin:**
1. Translate to Standard Mandarin first.
2. Apply Dongbei transforms as above.

---

## Step 4: Output

1. **File output:** Save to `_dongbei` suffix (e.g., `article.md` →
   `article_dongbei.md`). If no file was provided, output directly in
   conversation.
2. **Show 3-5 representative sentence pairs** comparing Original and Dongbei.
3. **List applied patterns:** Note which major pattern groups (G/V/S) were most
   active and why.
4. **Glossary:** List signature 標誌詞 used （整 / 賊 / 嘎哈 / 咋整 / 老鐵 / 妥妥
   / 杠杠 / 必須 etc.) with brief explanations.

---

## Checklist — 21 條

### Grammar
- **G-01** [Hard, Light+] 「整」字至少出現一次（替代做 / 弄 / 辦 / 搞）
- **G-02** [Hard, Light+] 「賊」+ 形容詞 ≥ 1 次（替代很 / 非常）
- **G-03** [Hard, Light+] 老 X / 小 X / 大兄弟 / 老鐵 框架使用 ≥ 1 次
- **G-04** [Hard, Medium+] 「給我 / 給你」語氣框架使用得當（不濫用）
- **G-05** [Hard, Light+] 反問句 / 雙重否定使用 ≥ 1 次
- **G-06** [Soft, Medium+] V V 兒重疊出現 ≥ 1 次（嘮嘮兒 / 整整兒 / 瞅瞅兒）
- **G-07** [Hard, Medium+] 「可 X」副詞使用得當
- **G-08** [Hard, Light+] 「咱／咱們／咱倆／咱大伙兒」共謀感人稱框架使用 ≥ 1 次（東北話比普通話更頻繁用「咱」拉近距離）

### Vocabulary
- **V-01** [Hard, Light+] 標誌動詞（嘎哈 / 咋整 / 瞅 / 嘮 / 忽悠 / 整事兒）出現 ≥ 1 次
- **V-02** [Hard, Light+] 程度詞（賊 / 老 / 杠杠的 / 妥妥的）出現 ≥ 2 個不同
- **V-03** [Hard, Medium+] 滿 / 蒙 / 俄借詞 ≥ 1 次（嘎拉哈 / 列巴 / 摳搜 / 咋呼）
- **V-04** [Hard, Light+] 口頭禪（必須的 / 妥了 / 嗯哪 / 那可不）出現 ≥ 1 次；文化詞補充：擼串兒 / 大碴子粥 / 暖氣 / 凍梨
- **V-05** [Hard, Medium+] 兒化分布合理（中等密度，不過度）

### Structure
- **S-01** [Hard, Light+] 句末助詞（唄 / 哈 / 啊 / 嗯哪）使用 ≥ 1 次，一句一個
- **S-02** [Hard, Medium+] 平均句長 ≤ 14 字，短促節奏
- **S-03** [Hard, Medium+] 反問 / 感嘆連珠 ≥ 1 處（高情緒時）
- **S-04** [Soft, Medium+] 擬聲詞（吭哧 / 嘎吱 / 咣噹）≥ 1 次（Heavy 必有）
- **S-05** [Hard, Light+] 口語開場詞（我跟你說 / 你還別說 / 那啥）≥ 1 次
- **S-06** [Soft, Medium+] 標點貼合短句節奏（不寫超長複句）

### Meta / 靈魂條款
- **M-01** [Hard, Light+] **全形標點零違規**——CJK 字之間 ASCII 半形 `, ; : ? !` 計數須為 0；blockquote CJK 段落單行不換行；全形標點與 CJK 之間零空格。以 Step 5 自檢指令驗證通過才算合格
- **M-02** [Hard, C-class] **東北口語節奏感**：必含 ≥ 3 處東北標誌詞（賊 / 嘎哈
  / 咋整 / 整 / 老鐵 / 啥的 / 妥妥的 / 杠杠的）+ 直爽強調語感（短促 + 階梯式
  推進）+ 口語化句末助詞（唄 / 哈 / 啊 / 嗯哪）。Light 每 5-6 句 1-2 處；
  Medium 每 2-3 句 1 處；Heavy 每句 1-2 處 + 助詞密集。
- **M-03** [Hard, Light+] **禁止地域刻板印象**：不得把東北話寫成「粗魯 / 酗酒
  / 打架 / 沒文化」的代名詞，亦不得寫成黑社會 / 罪犯口吻。東北話是「東北官
  話地域文化現象」，是 二人轉 / 春晚小品 / 鄉村愛情 那條溫暖、自嘲、直爽的
  口語傳統。當源文與這些 stereotype 無關時，改寫不得自行加入。
- **M-04** [Hard, Light+] 標誌詞分布**有節奏**，不可堆疊到讀來像在背詞典；助
  詞與口頭禪要鑲嵌進句意，不是貼標籤。

---

## Step 5: 9-step Workflow

1. **讀源文**：通讀全文，標出敘事節點、情緒高峰、對話段。
2. **選強度**：使用者指定？無則 Medium。Light 給溫和場合，Heavy 給有舞台感的
   段落。
3. **標可改寫處**：把可換為「整」的動詞、可加「賊」的形容詞、可換成「老 X /
   咋整 / 嘎哈」的句式劃出來。
4. **替換詞彙**：依 V1-V5 替換。注意不過度換——保留書面語錨點，避免讀來像
   詞典條目。
5. **改造句式**：把長複句切成短句（S2），加反問（G5、S3），加開場詞（S5）。
6. **加語助詞與口頭禪**：依 S1 / V5 鑲嵌，一句一個，不堆疊。
7. **檢查標誌詞密度**：對照 M-02 的強度規範，密度過低補；過高刪。
8. **標點清理**：對照 M-01 與 S-06，全形標點、blockquote 不換行、短句節奏。**寫完後必跑自檢指令**：

   ```bash
   python3 -c "
   import re, sys
   text = open(sys.argv[1]).read()
   bad = re.findall(r'[^\x00-\x7f][,;:?!][^\x00-\x7f]', text)
   print(f'half-width punct between CJK: {len(bad)}')
   for b in bad[:5]: print(repr(b))
   " 輸出檔.md
   ```

   結果必須為 `0`。非 0 表示輸出時混入了 ASCII 半形於 CJK 字之間，逐字替換後重跑，直到歸零才算交付。
9. **朗讀檢查節奏**：心中默讀一遍——能不能想像一個東北人這樣說？卡到的地方
   退回去調節奏。

---

## Anti-patterns（常見失敗模式）

寫完一稿、自檢之前，先掃一眼這條最容易踩的坑：

1. **半形標點混入** — 輸出時把 `,;:?!` 打成 ASCII 半形而非全形 `，；：？！`。
   常見原因是 IME 切換失誤或從英文 prompt 複製字串。M-01 已明文要求全形；
   寫完務必跑 Step 5 自檢指令，計數歸零才算交付。

---

## Important Notes

- **這是風格轉換工具**，用於創意寫作、文化欣賞、語言教育。
- **東北話是合法語言變體**，不是「不標準的普通話」。它有自己的語音系統、詞
  彙系統、語用節奏，且承載著 二人轉 / 春晚 / 鄉村愛情 / 直播 短視頻 等豐富
  口語表演傳統。
- **避免地域刻板印象**：M-03 是 Hard rule。不寫「粗魯 / 酗酒 / 打架 / 沒文
  化」的東北人形象。當源文是中性敘事，改寫保持中性；當源文已有這類元素，
  也只還原源文的語氣，不放大。
- **整 / 賊 / 嘎哈 不是裝飾**：它們是語法功能詞——整是動詞替換、賊是程度詞、
  嘎哈是疑問詞。把它們鑲在功能位上，不是貼在句末當印章。
- **句末助詞不混用**：唄（建議 / 接受）、哈（確認 / 親近）、啊（強調 / 開
  場）、嗯哪（應答）。一句一個，不堆疊。
- **兒化要節制**：東北話兒化中等密度，過度兒化會偏向老北京。Light 每 4-6 句
  一個，Medium 每 2-3 句，Heavy 自由但仍要有節奏。
- **正式 / 古典文本警告**：法律合約、古典詩詞、政府公文改寫成東北話會產生
  喜劇效果而非實用結果。改寫前提醒使用者。
- 拿不準時想：**「《鄉村愛情》裡哪個角色會這麼說？」「趙本山小品開場第一
  句會怎麼起？」「直播間老鐵會怎麼接？」** 那就是要的口吻。
