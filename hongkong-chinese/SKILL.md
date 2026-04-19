---
name: hongkong-chinese
description: >
  Transform text into Hong Kong Written Chinese (港式中文) — a written register of
  Modern Standard Chinese shaped by Cantonese substrate, English contact, and
  Hong Kong-specific social vocabulary. Features Hong Kong-specific terms
  (巴士/的士/士多/雪櫃), transliterations (荷里活/三文治/梳化), Cantonese lexical
  intrusions (食飯/飲茶/睇/搞掂/啲/嘢), frequent code-mixing with English
  (開 meeting / send email), and AB/BA word-order flips (質素/私隱/擠擁).
  Preserves standard Chinese grammar backbone (是/不/的/了/他) — distinct from
  fully Cantonese-written text. Three intensity levels from light HK flavor
  to heavy code-mixed text.
  Useful for creative writing, cultural appreciation, language education, or humor.
  Triggers on "/hongkong-chinese", "寫成港式中文", "港式中文化", "翻成港式中文",
  "translate to hong kong chinese", "make it hong kong style", "港式書面語", "港味".
argument-hint: [file-path]
allowed-tools: Read, Write, Edit, Glob
---

# Hong Kong Chinese — 港式中文

Transform text into Hong Kong Written Chinese (港式中文) — the written variety of
Modern Standard Chinese used in Hong Kong, shaped by decades of Cantonese substrate,
English contact, and Hong Kong-specific social vocabulary. The result should read
like a Hong Kong newspaper column, a Cantopop lyric sheet, or a WhatsApp message
from a HK colleague — recognizably Chinese in grammar, unmistakably HK in flavor.

Hong Kong Chinese is NOT written Cantonese. It preserves the Standard Written
Chinese grammatical backbone (是/不/沒/的/了/他/這/那) while adopting Cantonese
lexicon (食/飲/睇/搞掂), Hong Kong-specific terms (巴士/的士/雪櫃), unique
transliterations (荷里活/三文治), and pervasive English code-mixing. For full
Cantonese writing with 係/唔/嘅/咗/佢/呢/嗰 throughout, a separate `written-cantonese`
skill would be more appropriate.

## Scope boundary

| | 港式中文（this skill） | 粵語書面化（out of scope） |
|---|---|---|
| 是 | 仍用「是」 | 全用「係」 |
| 不 / 沒 | 仍用「不 / 沒」 | 全用「唔 / 冇」 |
| 的 / 了 | 仍用「的 / 了」 | 全用「嘅 / 咗」 |
| 他 / 她 | 仍用「他 / 她」 | 全用「佢」 |
| 這 / 那 | 仍用「這 / 那」 | 全用「呢 / 嗰」 |
| 食 / 飲 / 睇 | 可偶用或全用 | 全用 |
| 啲 / 嘢 / 搞掂 | 可散用 | 全用 |
| 中英夾雜 | 常見 | 常見 |

In other words: a HK reader of this skill's output recognizes it as a "HK-flavored"
variety of Standard Written Chinese. A Mandarin reader from Taiwan or mainland China
can still parse it, perhaps with some unfamiliar vocabulary. If they cannot parse it,
the skill has crossed into 粵語書面化 territory and needs to be pulled back.

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
and transliterations) to heavy code-mixing with Cantonese lexicon peppered throughout.
This skill targets that full range.

---

### Grammar Patterns（語法模式）

#### G1. 西化結構 — 受英語影響的句式 [Hard, Medium+]

Hong Kong Chinese has absorbed English-influenced sentence structures through long
contact. Long attributive modifiers, passive constructions, and abstract nominalizations
are more common than in Taiwan Mandarin.

> **Standard:** 這個提案值得討論。
>
> **HK Chinese:** 這個提案係有討論嘅價值嘅。 (過重時回退到「值得討論」)

> **Standard:** 請盡快回覆。
>
> **HK Chinese:** 請 ASAP 俾個 reply 我。

> **Standard:** 他被選為主席。
>
> **HK Chinese:** 佢被選為 chairman / 佢畀人選為主席。

Use西化結構 lightly — overuse slides into translationese, not HK Chinese.

#### G2. 「有 / 冇」+ 動詞 — 動作完成或經驗 [Hard, Medium+]

Cantonese 有/冇 + V marks completion or existence. HK Chinese inherits this pattern
in writing. At Medium, mix 有 with 了/過; at Heavy, use 有 freely.

> **Standard:** 我去過日本。
>
> **HK Chinese:** 我有去過日本。

> **Standard:** 他沒吃飯。
>
> **HK Chinese:** 佢冇食飯。 (Heavy) / 他沒食飯。 (Medium)

#### G3. 畀 / 俾 — 「給」的港式寫法 [Soft, Medium+]

HK Chinese often writes 畀 (or 俾) for "give / to / by" instead of Standard 給/被.

> **Standard:** 這本書給你。
>
> **HK Chinese:** 呢本書畀你。 / 這本書畀你。

> **Standard:** 他被老闆罵了。
>
> **HK Chinese:** 佢畀老闆鬧。 / 他畀老闆鬧。

#### G4. 動詞 + 得 / 唔 — 可能補語 [Soft, Heavy]

Cantonese-style possibility compounds enter HK writing at Heavy intensity.

> **Standard:** 我做不到。
>
> **HK Chinese (Heavy):** 我做唔到。

> **Standard:** 看得懂。
>
> **HK Chinese (Heavy):** 睇得明。

At Medium, stick with Standard 做不到 / 看得懂; only slide into 唔 forms when the
overall tone is heavily Cantonese.

#### G5. 句末「嘅」/「㗎」/「啦」/「囉」/「喎」[Soft, Heavy]

Sentence-final particles from Cantonese. Use them sparingly — stacking too many
particles pushes the text into 粵語書面化 rather than港式中文.

| 粒子 | 功能 |
|---|---|
| 嘅 | 陳述/屬性（對應「的」，句末時含強調） |
| 㗎 | 強調、自信 |
| 啦 | 緩和、催促 |
| 囉 | 認命、無奈 |
| 喎 | 訝異、提醒 |

> **Standard:** 就是這樣。
>
> **HK Chinese:** 就係咁㗎啦。 (Heavy) — note 係/咁 already粵語化

**Medium rule:** at most one Cantonese particle per paragraph; otherwise pull back
to 標點 or「啊/呢」.

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
| 平治 | 賓士（汽車） |
| 寶馬 | BMW（港音譯） |

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
| 去返 | 回去 |
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

**Morphological quirk:** HK English borrowings often gain a Cantonese suffix syllable
(mon1 for "monitor", kon1 si2 for "constitution"). This is mostly spoken, but
occasional spellings like 「個 mon」appear in casual text.

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
| 氣氛 (same) | 氣氛 |
| 相片 | 照片 |
| 天花 | 天花板 |
| 紙巾 | 餐巾紙（不同意） |

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
Chinese voice — identifiably Hong Kong, but still readable as Chinese (not fully
Cantonese-written).

### Intensity Levels

Each rule is tagged with its minimum intensity. Maintain the **scope boundary**:
at every level, preserve 是/不/沒/的/了/他 — do not let the text collapse into
粵語書面化.

| Level | Active Rules | Effect |
|---|---|---|
| **Light** | V1, V2, V5 (1-2 English words/paragraph), S3. No 粵字, no 傳承詞. | Standard Written Chinese with HK-specific vocabulary and transliterations sprinkled in — like a HK business email. |
| **Medium** (default) | Light + G1-G3, V3-V4 (選擇性粵字), V6-V9, V5 (pervasive code-mixing), S1-S2, S4 (sparing). | Clearly HK-flavored — HK terms, Cantonese vocabulary, frequent English code-mixing, word-order flips, HK social vocabulary. |
| **Heavy** | Medium + G4-G5 (Cantonese particles/possibility compounds), V4 full (啲/嘢/點解 everywhere), S4 liberal. Still preserves 是/不/的/了/他. | Heavy HK writing — reads like a casual blog post, Apple Daily column, or LIHKG post. Still distinguishable from full written Cantonese. |

If the user doesn't specify, use **Medium**.

### Input-Specific Handling

**Mandarin input → HK Chinese:**
1. Swap HK-specific terms (V1, V2).
2. Replace key verbs with 傳承詞 where natural (食/飲/睇/瞓/行/企).
3. Inject English code-mixing per intensity (V5).
4. Flip word order for AB/BA pairs (V7).
5. Add selective 粵字 (啲/嘢/點解/搞掂) at Medium; more at Heavy.
6. Keep 是/不/沒/的/了/他 — do NOT auto-swap to 係/唔/冇/嘅/咗/佢.

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
  it is recognized by linguists (e.g., 邵敬敏) as 現代漢語 in 香港 variety, with地域、
  社會、功能三位一體的變體性質.
- **Preserve the grammatical backbone.** The key distinguishing feature of港式中文
  (vs 粵語書面化) is that it keeps 是/不/沒/的/了/他. If Heavy mode accidentally
  swaps these to 係/唔/冇/嘅/咗/佢, pull back — that crosses into a different skill's
  scope.
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
