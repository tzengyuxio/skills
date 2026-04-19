---
name: hongkong-chinese
description: >
  Transform text into Hong Kong Chinese (港式中文) — a written register shaped by
  Cantonese substrate, English contact, and Hong Kong-specific social vocabulary.
  Features Hong Kong-specific terms (巴士/的士/士多/雪櫃), transliterations
  (荷里活/三文治/梳化), Cantonese lexicon (食飯/飲茶/睇/搞掂/啲/嘢),
  frequent English code-mixing (開 meeting / send email), AB/BA word-order flips
  (質素/私隱/擠擁), and — at Heavy intensity — optional full Cantonese-written
  features (係/唔/嘅/咗/佢/呢/嗰). Three intensity levels from light HK flavor
  (standard Chinese backbone) to heavy 港式粵語混合體.
  Useful for creative writing, cultural appreciation, language education, or humor.
  Triggers on "/hongkong-chinese", "寫成港式中文", "港式中文化", "翻成港式中文",
  "translate to hong kong chinese", "make it hong kong style", "港式書面語", "港味".
argument-hint: [file-path]
allowed-tools: Read, Write, Edit, Glob
---

# Hong Kong Chinese — 港式中文

Transform text into Hong Kong Chinese (港式中文) — the written variety used in
Hong Kong, shaped by decades of Cantonese substrate, English contact, and
HK-specific social vocabulary. The result should read like a Hong Kong newspaper
column, a Cantopop lyric sheet, a LIHKG post, or a WhatsApp message from a HK
colleague — unmistakably HK in flavor, flexibly sliding from standard Chinese
backbone (formal register) to full 港式粵語混合體 (casual register).

This skill covers the **full continuum** from light HK-flavored Standard Chinese
up to heavy Cantonese-written text. At Light intensity, the output retains
Standard Written Chinese backbone (是/不/的/了/他); at Heavy, it may slide fully
into 粵語書面化 features (係/唔/嘅/咗/佢/呢/嗰). Users select intensity based
on the target register.

## Scope and intensity range

| 層面 | Light | Medium | Heavy |
|---|---|---|---|
| 是 / 不 / 沒 | 保留 | 大部分保留，偶見粵字 | 可全改「係 / 唔 / 冇」 |
| 的 / 了 | 保留 | 混用 | 可全改「嘅 / 咗」 |
| 他 / 這 / 那 | 保留 | 混用 | 可全改「佢 / 呢 / 嗰」 |
| 食 / 飲 / 睇 / 行 | 偶用 | 常用 | 全用 |
| 啲 / 嘢 / 點解 / 搞掂 | 不用 | 選擇性使用 | 自由使用 |
| 中英夾雜 | 低（每段 1-2 字） | 中（每段 3-5 字） | 高（每 2-3 句出現） |
| 粵式句末助詞（嘅/㗎/啦/囉/喎） | 不用 | 稀疏 | 常用 |

See the **Intensity Levels** section below for which rule groups activate at each
level, and **Important Notes** for the forward compatibility note with a future
`written-cantonese` skill.

## Arguments

- `$0` — (Optional) Path to a markdown or text file. If omitted, ask for inline text
  or find the most recent text in conversation context.

## Step 1: Load the Text

- If `$0` is provided, read the file.
- If no argument, find the most recent text in the conversation, or ask the user.
- The input can be **Standard Written Chinese** (rewrite as HK Chinese), **any
  language** (translate to HK Chinese), or **English** (translate to HK Chinese).

## Step 2: Apply Hong Kong Chinese Patterns

Apply the rules below systematically. Goal: every paragraph should carry at least
one HK marker (a HK-specific term, a transliteration, a code-mixed English word, or
a word-order flip). Not every rule applies to every sentence — select what fits
naturally.

Hong Kong Chinese exists on a continuum from light HK flavor (occasional HK terms
and transliterations on a Standard Chinese backbone) through medium code-mixing
with selective Cantonese vocabulary, to heavy 港式粵語混合體 where Cantonese
function words (係/唔/嘅/咗/佢/呢/嗰) and sentence particles (㗎/啦/囉/喎) appear
freely. This skill targets that full range.

---

### Grammar Patterns（語法模式）

#### G1. 西化結構 — 受英語影響的句式 [Hard, Medium+]

Hong Kong Chinese has absorbed English-influenced sentence structures through long
contact. Typical features: long attributive modifiers, abstract nominalizations,
passive constructions, and English-like clause ordering.

> **Standard:** 這個提案值得討論。
>
> **HK Chinese:** 這個提案具有重要的討論價值。 *(nominalization)*

> **Standard:** 他昨天晚上跟我說了這件事。
>
> **HK Chinese:** 他昨天晚上告訴了我一件關於那個項目的事情。 *(long definite NP)*

> **Standard:** 大家都很意外。
>
> **HK Chinese:** 這件事的發生令大家感到意外。 *(令-causative + nominalized subject)*

> **Standard:** 請盡快回覆。
>
> **HK Chinese:** 請於方便時盡快給予回覆。 *(formal nominalized)*

Use 西化結構 with restraint — overuse slides into 翻譯腔, not authentic HK Chinese.

#### G2. 「有 / 冇」+ 動詞 — 動作完成或經驗 [Hard, Medium+]

Cantonese 有/冇 + V marks completion or existence. HK Chinese inherits this pattern
in writing. Medium can adopt 有 for perfective while leaving other function words
alone; Heavy uses 冇 freely in place of 沒.

> **Standard:** 我去過日本。
>
> **HK Medium:** 我有去過日本。
>
> **HK Heavy:** 我有去過日本。 *(pattern stays the same; context around it shifts)*

> **Standard:** 他沒吃飯。
>
> **HK Medium:** 他還沒有食飯。 *(keep 他/沒; swap 吃 for 食)*
>
> **HK Heavy:** 佢冇食飯。

#### G3. 畀 / 俾 — 「給」的港式寫法 [Soft, Medium+]

HK Chinese often writes 畀 (or 俾) for "give / to / by" instead of Standard 給/被.

> **Standard:** 這本書給你。
>
> **HK Chinese:** 呢本書畀你。 / 這本書畀你。

> **Standard:** 他被老闆罵了。
>
> **HK Chinese:** 佢畀老闆鬧。 / 他畀老闆鬧。

#### G4. 動詞 + 得 / 唔 — 可能補語 [Soft, Medium+]

Cantonese-style possibility compounds. Medium: occasional; Heavy: routine.

> **Standard:** 我做不到。
>
> **HK Chinese:** 我做唔到。

> **Standard:** 看得懂。
>
> **HK Chinese:** 睇得明。

> **Standard:** 吃不下。
>
> **HK Chinese:** 食唔落。

#### G5. 句末「嘅」/「㗎」/「啦」/「囉」/「喎」[Soft, Medium+]

Sentence-final particles from Cantonese. Medium: use sparingly; Heavy: use freely.

| 粒子 | 功能 |
|---|---|
| 嘅 | 陳述/屬性（對應「的」，句末時含強調） |
| 㗎 | 強調、自信 |
| 啦 | 緩和、催促 |
| 囉 | 認命、無奈 |
| 喎 | 訝異、提醒 |
| 咋 | 限定（只是/而已） |
| 啩 | 推測 |

> **Standard:** 就是這樣。
>
> **HK Medium:** 就係咁樣。
>
> **HK Heavy:** 就係咁㗎啦。

#### G6. 粵語核心虛詞替換 [Hard, Medium+]

Cantonese-specific function words replace Mandarin equivalents. The degree of
replacement scales sharply with intensity — selective at Medium (a few set phrases
and demonstratives), comprehensive at Heavy (full Cantonese backbone).

| 標準中文 | 粵語書寫 | 使用建議 |
|---|---|---|
| 是 | 係 | Medium 稀疏，Heavy 多用 |
| 不 | 唔 | Medium 可用於常見搭配（唔該/唔使/唔記得），Heavy 自由 |
| 沒（有） | 冇 | Medium 可用，Heavy 常用 |
| 的 | 嘅 | Medium 稀疏，Heavy 多用 |
| 了 | 咗 | Heavy 常用 |
| 著（進行） | 緊 / 住 | Heavy（食緊飯 / 著住衫） |
| 他 / 她 | 佢 | Heavy 常用 |
| 這 / 這個 | 呢 / 呢個 | Medium 可用，Heavy 常用 |
| 那 / 那個 | 嗰 / 嗰個 | 同上 |
| 和 | 同 | Medium 可用 |
| 都（全都） | 都 | 相同，用法更自由 |
| 也 | 都 / 亦 | |
| 給 | 畀 / 俾 | 見 G3 |
| 很 | 好 | Medium 常用（好靚 / 好鬼好食） |

**Intensity strategy:**
- Light: none of G6 swaps — keep Standard backbone
- Medium: selective swaps — use 呢/嗰、唔、冇 where natural; keep 是/的/了/他 mostly
- Heavy: full swap allowed — 係/唔/冇/嘅/咗/佢/呢/嗰 throughout

---

### Vocabulary Patterns（詞彙模式）

#### V1. 港式常用詞 vs 現代漢語（形式相異，意義相同）[Hard, Light+]

The most recognizable signature of HK Chinese. Swap these freely.

| 港式中文 | 現代漢語 / 台灣 |
|---|---|
| 巴士 | 公共汽車 / 公車 |
| 的士 | 計程車 / 出租車 |
| 小巴 | 小型公車 |
| 單車 | 腳踏車 / 自行車 |
| 士多 | 小賣部 |
| 夾萬 | 保險箱 |
| 唇膏 | 口紅 |
| 手袋 | 手提包 |
| 尾站 | 終點站 |
| 見工 | 面試 |
| 雪櫃 | 冰箱 |
| 冷氣 | 空調 |
| 擦膠 | 橡皮擦 |
| 書釘 | 訂書針 |
| 原子筆 | 圓珠筆 |
| 八達通 | 交通卡（港獨有） |

#### V2. 港式音譯詞 [Hard, Light+]

HK has its own transliteration tradition, distinct from both Mainland and Taiwan.

| 港式音譯 | 現代漢語 / 原文 |
|---|---|
| 荷里活 | 好萊塢 Hollywood |
| 梳化 | 沙發 sofa |
| 三文治 | 三明治 sandwich |
| 多士 | 吐司 toast |
| 忌廉 | 奶油 cream |
| 朱古力 | 巧克力 chocolate |
| 結他 | 吉他 guitar |
| 貼士 | 小費 / 提示 tips |
| 士多啤梨 | 草莓 strawberry |
| 布冧 | 李子 plum |
| 車厘子 | 櫻桃 cherry |
| 芝士 | 起司 cheese |
| 咖喱 | 咖哩 curry |
| 比堅尼 | 比基尼 bikini |
| 的士高 | 迪斯可 disco |
| 菲林 | 底片 film |
| 啤梨 | 梨 pear |
| 士巴拿 | 扳手 spanner |
| 鐳射 | 激光 laser |
| 波士 | 老闆 boss |
| 平治 | 賓士 Mercedes-Benz |
| 寶馬 | BMW（港音譯，普通話亦同字但讀音不同） |

#### V3. 傳承詞（文言遺留 / 粵語保留的古語）[Hard, Medium+]

HK Chinese retains many single-character verbs that Mandarin has replaced with
bisyllabic or different forms. These read naturally in HK writing and are
linguistically "old Chinese", not "broken Chinese".

| 港式 | 現代漢語 |
|---|---|
| 食（飯） | 吃（飯） |
| 飲（茶） | 喝（茶） |
| 睇（書/戲） | 看（書/電影） |
| 瞓（覺） | 睡（覺） |
| 行（路） | 走（路） |
| 企（喺度） | 站（著） |
| 講 | 說 |
| 畀 / 俾 | 給 |
| 嚟 | 來 |
| 返去 | 回去 |
| 返工 | 上班 |
| 收工 | 下班 |
| 攞 | 拿 |
| 揾 | 找 |

#### V4. 粵字選擇性入文 [Soft, Medium+]

A handful of Cantonese characters enter HK Chinese without fully cantonizing the text.
Unlike 粵語書面化 (which uses 嘅/咗/緊/係/唔 throughout), HK Chinese uses these
selectively.

| 粵字 | 意思 | 可用性 |
|---|---|---|
| 啲 | 一些、一點 | 常見 |
| 嘢 | 東西 | 常見 |
| 點 / 點解 | 怎麼 / 為什麼 | 常見 |
| 邊 / 邊度 | 哪 / 哪裡 | 偶見 |
| 幾 | 多（程度副詞） | 常見 |
| 搞掂 | 搞定、完成 | 常見 |
| 有型 | 有型、帥氣 | 常見 |
| 好正 | 非常棒 | 常見 |
| 靚 | 漂亮 / 好 | 常見 |
| 勁 | 厲害 | 常見 |

> **Standard:** 這件事真的很麻煩。
>
> **HK Chinese:** 呢單嘢真係好煩啊。 (Heavy) /  這單嘢真的很煩。 (Medium)

#### V5. 中英夾雜（Code-mixing）[Hard, Light+]

One of the most visible features of HK writing. Insert English words for nouns
(meeting, project, email, office, deadline), verbs (check, confirm, book, send,
update), and adjectives (OK, fine, so-so, cool).

Orthographic convention: English words appear in Latin script, not transliterated,
and usually keep their English spelling intact.

| 場景 | 港式句 |
|---|---|
| 辦公 | 我返 office 開 meeting。 |
| 通訊 | Send 個 email 俾佢 confirm 一下。 |
| 購物 | 個 size 啱唔啱？個 price 幾多？ |
| 社交 | 我哋今晚去 book 間餐廳。 |
| 評價 | 呢個 presentation 幾 OK 喎。 |
| 動作 | Check 吓個 project 嘅 progress。 |

**Intensity guidance:**
- Light: 1-2 English words per paragraph, mostly nouns (office, meeting)
- Medium: 3-5 per paragraph, including verbs (check, send, book)
- Heavy: pervasive — every 2-3 sentences have English insertion

#### V6. 社區詞（HK-specific social vocabulary）[Hard, Medium+]

Words unique to HK society, reflecting local culture, institutions, and stereotypes.

| 社區詞 | 意思 |
|---|---|
| 打工皇帝 | 高薪受僱者 |
| 鑽石王老五 | 黃金單身漢 |
| 炒魷魚 | 解僱 |
| 電話粥 | 長時間講電話 |
| 大閘蟹 | 被套牢的股民 |
| 魚腩 | 弱勢、任人宰割 |
| 偷雞 | 投機取巧 |
| 走鬼 | 小販逃避執法 |
| 走光 | 曝光（衣著） |
| 廢青 | 無所事事的青年 |
| 港女 / 港男 | 典型 HK 女/男 |
| 離地 | 脫離現實 |
| 離曬大譜 | 太過分 |
| 九唔搭八 | 牛頭不對馬嘴 |
| 論盡 | 笨拙、麻煩 |
| 搞搞震 | 搞亂、搗蛋 |
| 頂硬上 | 硬著頭皮上 |
| 爆煲 | 事情爆發 |

#### V7. 詞序倒置（AB / BA flip）[Hard, Medium+]

HK Chinese retains or adopts AB order where Mandarin uses BA (or vice versa).
These are fully acceptable in HK formal writing.

| 港式 | 現代漢語 |
|---|---|
| 質素 | 素質 |
| 銜頭 | 頭銜 |
| 私隱 | 隱私 |
| 擠擁 | 擁擠 |
| 取錄 | 錄取 |
| 飯盒 | 盒飯 |
| 相片 | 照片 |
| 天花 | 天花板 |

#### V8. 同形異義詞 — 港式特有意義 [Soft, Medium+]

Words that look the same but carry different meanings in HK vs 現代漢語. Use in HK
sense when targeting HK context.

| 詞 | 港式意義 | 現代漢語意義 |
|---|---|---|
| 班房 | 課室 | 監獄 |
| 上堂 | 上課 | 打官司 |
| 婆婆 | 外婆 / 年長婦女 | 丈夫的母親 |
| 尾數 | 餘下的金額 | 小數點後數字 |
| 老婆 | 妻子 (HK 較隨意) | 妻子 (普通話家常) |
| 化學 (adj) | 變幻無常 / 經不起考驗 | 化學學科 |
| 陰濕 | 陰險奸詐（形容人） | 陰暗潮濕（形容天氣） |

> 「人生真的很化學。」 (HK: life is unpredictable / cheap quality)
> 「佢個人好陰濕。」 (HK: he is sneaky / underhanded)

#### V9. 詞語感情色彩差異 [Soft, Medium+]

Same word, different tone.

- **人士**: HK 用得寬鬆，可構成「服刑人士、自僱人士、游泳人士」。 Mandarin 多帶褒義。
- **檢討**: HK 多為中性「review / examine」。Mandarin 偏負面「self-criticism」。
- **理論上**: HK 偏中性。Mandarin 含「實際未必如此」的反諷色彩。

---

### Structure Patterns（結構模式）

#### S1. 量詞差異 [Hard, Medium+]

HK uses different measure words than Mandarin.

| 港式量詞 | 現代漢語 |
|---|---|
| 一隻（歌） | 一首 / 一支 |
| 一部（車） | 一輛 |
| 一啲（東西） | 一些 |
| 一齣（戲） | 一部 / 一場 |
| 一間（屋） | 一間 / 一棟 |
| 一嚿（飯） | 一塊 / 一團 (Heavy only) |

#### S2. 標題/告示公文套語 [Soft, Medium+]

HK formal writing retains文言 flavor in official contexts. Useful for news headlines
and公文 simulation.

| 套語 | 意思 |
|---|---|
| 視乎 | 取決於 |
| 合乎 | 符合 |
| 抑或 | 或者 |
| 毋須 | 不必 |
| 如屬 | 如果是 |
| 就此 | 關於這件事 |
| 有關 (前置) | 作為介詞：「有關此事」 |
| 茲 | 正式開頭 |

> 「政府毋須就此作出回應，視乎立法會表決結果而定。」

#### S3. 英文名稱保留原文 [Hard, Light+]

HK writing keeps English proper nouns in Latin script, rarely transliterating them.
Company names, product names, places outside HK, technical terms.

> 「我哋用 Slack 同 Notion 做 project management。」
>
> 「IKEA 啲 furniture 唔錯。」
>
> 「去 Starbucks 買杯 cappuccino。」

#### S4. 粵式感嘆 / 開場詞 [Soft, Heavy]

| 詞 | 場合 |
|---|---|
| 嘩 | 驚嘆 |
| 哎吔 | 不悅 / 驚訝 |
| 頂 | 抱怨（粗俗） |
| 仆街 | 糟糕（粗俗） |
| 屌 | 驚嘆（粗俗） |
| 好彩 | 幸好 |
| 邊個話 | 誰說的 |

Use sparingly in Medium; more freely in Heavy.

---

## Step 3: Produce Hong Kong Chinese Output

Apply the checklist to transform the entire text. Aim for a natural, consistent HK
Chinese voice at the chosen intensity — from formal HK-flavored Standard Chinese
to casual 港式粵語混合體.

### Intensity Levels

Each rule is tagged with its minimum intensity. Intensity controls how far the
text slides from Standard Chinese backbone toward full Cantonese-written forms.

| Level | Active Rules | Effect |
|---|---|---|
| **Light** | V1, V2, V5 (1-2 English words/paragraph), S3. No 粵字, no 傳承詞, no G6 function word swaps. | Standard Written Chinese with HK-specific vocabulary and transliterations sprinkled in — like a HK business email or government notice. |
| **Medium** (default) | Light + G1-G3, G5-G6 (selective), V3-V4 (選擇性粵字), V6-V9, V5 (pervasive code-mixing), S1-S2, S4 (sparing). | Clearly HK-flavored — HK terms, Cantonese vocabulary, frequent English code-mixing, word-order flips, selective 粵字/虛詞 where natural. Mixed backbone. |
| **Heavy** | All rules including G4-G6 full (係/唔/冇/嘅/咗/佢/呢/嗰 throughout), V4 full (啲/嘢/點解 everywhere), G5 liberal particles, S4 liberal. | Heavy HK writing — reads like a LIHKG post, casual column, or WhatsApp conversation. Backbone may be fully Cantonese-written. |

If the user doesn't specify, use **Medium**.

### Input-Specific Handling

**Mandarin input → HK Chinese:**
1. Swap HK-specific terms (V1, V2).
2. Replace key verbs with 傳承詞 where natural (食/飲/睇/瞓/行/企).
3. Inject English code-mixing per intensity (V5).
4. Flip word order for AB/BA pairs (V7).
5. Add selective 粵字 (啲/嘢/點解/搞掂) at Medium; more at Heavy.
6. Apply G6 function word swaps per intensity:
   - Light: keep Standard 是/不/沒/的/了/他/這/那
   - Medium: swap selectively (e.g., 呢/嗰 common, 唔 in set phrases, keep 是/的/了 mostly)
   - Heavy: swap freely to 係/唔/冇/嘅/咗/佢/呢/嗰

**Non-Chinese input → HK Chinese:**
1. Translate to Standard Written Chinese first.
2. Apply HK transforms as above.

---

## Step 4: Output

1. **File output:** Save to `_hongkong` suffix (e.g., `article.md` → `article_hongkong.md`).
   If no file was provided, output directly in conversation.
2. **Show 3-5 representative sentence pairs** comparing Original and HK Chinese.
3. **List applied patterns:** Note which major pattern groups (G/V/S) were most active.
4. **Glossary:** List HK-specific terms and transliterations used, with Mandarin
   equivalents.

---

## Important Notes

- This is a **stylistic transformation tool** for creative, educational, and cultural
  purposes.
- Hong Kong Chinese is a **legitimate written register** of Modern Standard Chinese —
  it is recognized by linguists (e.g., 邵敬敏) as 現代漢語 in 香港 variety, with 地域、
  社會、功能三位一體的變體性質. At the formal/書面 end (Light), it is close to Standard
  Chinese; at the casual/口語 end (Heavy), it slides into full 港式粵語混合體.
- **Match intensity to target register.** Light suits formal writing (news, government,
  business email); Medium suits journalism and blog posts; Heavy suits casual writing
  (LIHKG, WhatsApp, social media). Consistency within the chosen level matters more
  than strict boundary-keeping.
- **Future scope note.** If a dedicated `written-cantonese` skill is added, this
  skill's Heavy mode may be narrowed — leaving `hongkong-chinese` to cover Light-Medium
  (formal 港式中文 with Standard Chinese backbone) and `written-cantonese` to cover
  full 粵語書面化. For now, Heavy covers the full Cantonese-written range.
- **Code-mixing is not random.** English insertions tend to cluster in:
  - Workplace vocabulary (office, meeting, project, deadline, email, presentation)
  - Technology (send, check, update, book, confirm, OK)
  - Evaluation (fine, cool, so-so, weird)
  - Proper nouns (company, brand, place names)
- **Transliterations are fixed.** 荷里活 not 好萊塢, 梳化 not 沙發, 三文治 not
  三明治. Don't mix Taiwan/Mainland renderings.
- **Avoid caricature.** The goal is authentic HK writing — the style a HK journalist,
  student, or professional would produce — not exaggerated "HK-speak" stereotypes.
- When in doubt about word choice, think: "Would this appear in Apple Daily / Ming Pao
  / HK01 / a LIHKG post?" That's the register we target.
