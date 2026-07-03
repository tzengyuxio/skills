---
name: sichuan-mandarin
description: >
  Transform text into Sichuan Mandarin （四川話 / 川渝話） — a Southwestern Mandarin
  variety of the 成渝片 zone covering Sichuan and Chongqing, marked by light
  「兒」化，莫/莫得 negation, abundant sentence-final particles （嘛/噻/嘞/哈/撒）,
  signature lexicon （巴適/安逸/莫得/搞快點/龜兒/撇脫/擺龍門陣/牙尖/假打/鬼火冒）,
  blunt 江湖 humor, and a self-mocking 川劇丑角 voice. Three intensity levels
  from light Sichuan flavor on a Putonghua backbone to heavy 張麻子-style
  江湖 cadence. Useful for creative writing, cultural appreciation, language
  education, or humor.
  Triggers on "/sichuan-mandarin", "寫成四川話", "川話化", "翻成川話", "重慶話",
  "translate to sichuan mandarin", "make it sichuan", "巴適", "龜兒", "西南官話",
  "火鍋英雄風", "讓子彈飛口吻".
license: PolyForm Noncommercial 1.0.0
argument-hint: "[file-path]"
allowed-tools: Read, Write, Edit, Glob
---

# Sichuan Mandarin — 四川話 / 川渝話

Transform text into Sichuan Mandarin （四川話） — the Southwestern Mandarin variety
spoken across Sichuan and Chongqing in the 成渝片 zone. The result should read
like a Chengdu 茶館 regular cracking jokes, a Chongqing 火鍋 boss yelling at
the kitchen, or 張麻子 in《讓子彈飛》laying down the law — direct, salted with
江湖 humor, and unmistakably 川渝.

四川話 is **NOT** broken Putonghua, nor is it the cartoon "麻將-and-火鍋"
caricature pinned on Sichuan in TV comedy. It is a real Mandarin variety with
its own phonology, lexicon, and pragmatic particle stack. Most speakers can
also read and write Putonghua; this skill targets the **written representation**
of casual 川渝 speech — the way those phonetic and lexical features surface
in text messages, novels, screenplay dialogue, and online posts.

## Arguments

- `$0` — (Optional) Path to a markdown or text file. If omitted, ask for inline
  text or find the most recent text in conversation context.

## Step 1: Load the Text

- If `$0` is provided, read the file.
- If no argument, find the most recent text in the conversation, or ask the user.
- The input can be **Mandarin Chinese** (rewrite as Sichuan Mandarin), **any
  language** (translate to Sichuan Mandarin), or **English** (translate to
  Sichuan Mandarin).

## Step 2: Apply Sichuan Mandarin Patterns

Apply the rules below systematically. Goal: every 2-3 sentences should carry
at least one 川渝 marker — a signature word, a 莫/莫得 negation, a 嘛/噻/嘞/哈
particle, a 「兒」化 ending, or a 江湖-toned construction. Not every rule applies
to every sentence — pick what fits naturally.

四川話 sits on a continuum from light flavor (a few signature words on an
otherwise standard backbone) up to heavy 江湖 cadence with 川劇丑角 self-mockery.
This skill targets that full range, deliberately avoiding stereotype-laden
caricature (lazy / mahjong-addicted / hotpot-obsessed tropes).

---

### Soul Clause — 川渝江湖氣 [C-class Hard, all intensities]

The output **must** carry the 川渝 江湖+幽默口語 voice. Concretely, every
piece of meaningful Medium/Heavy output must contain:

1. **≥3 signature lexical markers** drawn from {巴適，安逸，莫得，搞快點，龜兒，
   撇脫，擺龍門陣，牙尖，假打，鬼火冒，哦豁，板眼兒，瓜娃子}.
2. **「兒」化 density above Putonghua** — Sichuan 兒化 is restricted (only 4
   韻尾） but pervasive in the slots it occupies: place names （成都兒，重慶兒）,
   small objects （雞蛋兒，板凳兒，棍兒，缽兒）, playful adjectives （好玩兒，
   乖乖兒）.
3. **≥1 句末助詞** per ~2 sentences, drawn from {嘛，噻，嘞，哈，撒，喲，哦}.
4. **江湖+自嘲 cadence** — short blunt clauses, rhetorical 反問， the speaker
   willing to throw 「老子」 / 「龜兒」 at themselves and the world. The line
   between mock-anger and humor stays thin.

If the output lacks the soul clause, it is not 四川話 — it is only Putonghua
with a few words swapped.

---

### Grammar Patterns（語法模式）

#### G1. 「莫 / 莫得」否定 [Hard, Light+]

四川話's most identifiable grammatical marker. 莫 = 沒 (negation of past /
existence); 莫得 = 沒有 (don't have).

> **Standard:** 我沒去。
>
> **Sichuan:** 我莫去。

> **Standard:** 沒有錢。
>
> **Sichuan:** 莫得錢。

> **Standard:** 沒辦法。
>
> **Sichuan:** 莫得辦法。 / 莫法。

「莫」also doubles as a soft prohibitive (= 別 / 不要）:

> **Standard:** 別亂說。
>
> **Sichuan:** 莫亂說嘛。

#### G2. 「兒」化 — 受限但頻繁 [Hard, Light+]

四川話 has only 4 兒化 韻尾 (vs. Beijing's 26), but uses them densely in
specific slots. Add 兒 化 freely to:

| 類型 | 範例 |
|---|---|
| 地名 | 成都兒、重慶兒、府南河兒 |
| 小物件 | 雞蛋兒、板凳兒、缽兒、棍兒、刀兒、碗兒 |
| 親暱稱呼 | 妹兒、兒娃兒、男娃兒、女娃兒 |
| 形容詞輕語感 | 好玩兒、乖乖兒、慢慢兒、悄悄兒 |
| 量詞 | 一陣兒、一哈兒（一下兒）、一坨兒 |

Do **not** add 兒 to abstract nouns （思想兒 ✗) or actions （跑兒 ✗) — that
is northern Mandarin habit, not 川渝.

#### G3. 「搞」萬用動詞 [Hard, Light+]

「搞」is the 川渝 all-purpose verb — covers do/make/handle/mess-with. Often
combined with 快點/緊（趕緊）/啥子/這樣 for full sentences.

| 套式 | 意思 |
|---|---|
| 搞快點 | 趕緊、加速 |
| 搞啥子 | 在做什麼？ |
| 搞不贏 | 來不及、忙不過來 |
| 搞不來 | 不會做、做不來 |
| 亂搞 | 胡來 |
| 整 | 「搞」的近義詞，也常用 |

> **Standard:** 你在做什麼？
>
> **Sichuan:** 你搞啥子嘛？

> **Standard:** 快點啦。
>
> **Sichuan:** 搞快點噻！

#### G4. 反問 — 「啥子 / 咋個 / 哪個」 [Hard, Light+]

四川話 question words differ from Putonghua and ride a sharp rhetorical tone.

| 川渝 | 普通話 |
|---|---|
| 啥子 | 什麼 |
| 咋個 | 怎麼 / 怎麼辦 |
| 啷個 | 怎麼（變體） |
| 哪個 | 誰 / 哪一個 |
| 啥子時候 | 什麼時候 |
| 咋的嘛 | 怎麼樣？／敢怎樣？ |

> **Standard:** 你說什麼？
>
> **Sichuan:** 你說啥子？

> **Standard:** 那怎麼辦？
>
> **Sichuan:** 那咋個辦嘛？

#### G5. 動詞 + 「起 / 倒 / 起來」補語 [Soft, Medium+]

「起」「倒」 used as resultative or aspectual particles, slightly differently
from Putonghua.

> **Standard:** 拿著。
>
> **Sichuan:** 拿起。

> **Standard:** 站著。
>
> **Sichuan:** 站起。 / 杵到那兒。

> **Standard:** 我記得。
>
> **Sichuan:** 我記倒起的。

#### G6. 強化 — 「巴適得很 / 安逸慘了 / 扎實」[Hard, Light+]

四川話 favors postposed intensifiers, frequently stacking 「得很」, 「慘了」,
「扎實」 onto adjectives.

| 強化結構 | 範例 |
|---|---|
| X 得很 | 巴適得很、好吃得很、惱火得很 |
| X 慘了 | 累慘了、餓慘了、冷慘了 |
| 扎實 X | 扎實好吃、扎實惱火 |
| 好 X / 相當 X | 好巴適、相當安逸 |

> **Standard:** 非常舒服。
>
> **Sichuan:** 巴適得很。 / 安逸慘了。

> **Standard:** 太累了。
>
> **Sichuan:** 累慘了嘛。

#### G7. 「老子 / 龜兒」自稱與罵稱 [Hard, Medium+]

「老子」(self-reference, gruff first person) and 「龜兒」/「龜兒子」(2nd or
3rd person, mock-curse) are core 江湖 markers. They are blunt but not
necessarily hostile — among friends they are warm; in confrontation they
are sharp. Use sparingly in Light, freely in Medium/Heavy.

> **Self-reference (gruff):** 老子今天累慘了。
>
> **Mock-curse (friendly):** 龜兒子又遲到。
>
> **Real curse (sharp):** 龜兒，你給老子聽倒。

Note: not 1:1 with English curse equivalents. 「老子」 and 「龜兒」 are
emotionally calibrated by context and tone, not by intensity alone.

---

### Vocabulary Patterns（詞彙模式）

#### V1. 標誌詞 — Core Signature Set [Hard, Light+]

The most iconic 川渝 vocabulary. Sprinkle freely — these are not exotica,
they are everyday words.

| 川渝詞 | 意思 |
|---|---|
| 巴適 | 舒服、好、滿意 |
| 安逸 | 舒適、爽快、過癮 |
| 莫得 | 沒有 |
| 搞快點 | 趕緊、快一點 |
| 撇脫 | 乾脆、簡單俐落、爽快 |
| 擺龍門陣 | 聊天、講故事 |
| 牙尖 | 嘴尖、愛說、嘴利 |
| 假打 | 裝模作樣、虛偽 |
| 鬼火冒 | 火大、氣炸 |
| 哦豁 | 糟了、完蛋（驚嘆） |
| 板眼兒 | 名堂、花樣、本事 |
| 惱火 | 麻煩、棘手 |
| 造孽 | 可憐、慘 |
| 緊到 | 一直、不停地 |
| 慫 | 軟弱、孬 |

#### V2. 人稱與罵稱 [Hard, Medium+]

| 詞 | 意思 |
|---|---|
| 老子 | 我（粗豪） |
| 龜兒 / 龜兒子 | 罵語 / 戲稱 |
| 瓜娃子 | 笨蛋（多戲稱） |
| 瓜兮兮 | 傻乎乎 |
| 莽夫 | 魯莽的人 |
| 傻兒 | 傻子 |
| 妹兒 | 女孩 |
| 兒娃兒 | 男孩兒 |
| 婆娘 | 妻子 / 女人（口語） |
| 老漢兒 | 父親 |
| 婆婆 | 祖母 |

#### V3. 文化詞與生活詞 [Hard, Light+]

四川話's lexicon is densely tied to local culture. Use these for setting
without leaning on stereotype.

| 詞 | 意思 |
|---|---|
| 火鍋 | hot pot（共通詞，但語境上極具川渝代表性） |
| 麻辣燙 | 麻辣燙 |
| 串串兒 | 竹籤穿料的小火鍋 |
| 茶館 | 茶館（成都重要社交空間） |
| 擺龍門陣 | 聊天 |
| 川劇 | 川劇 |
| 變臉 | 變臉（川劇技藝） |
| 蓋碗 | 蓋碗茶 |
| 雞公車 | 獨輪推車（老式） |
| 黃桷樹 | 黃桷樹（川渝常見行道樹） |
| 巷子 | 巷子 |
| 壩壩 | 平地、廣場 |
| 院壩 | 院子 |

避免：把「打麻將、火鍋、懶散」做為角色性格的核心；那是刻板印象，不是 dialect。

#### V4. 程度副詞與口頭禪 [Hard, Light+]

| 詞/套式 | 用法 |
|---|---|
| 好 X | 好巴適、好辛苦 |
| 相當 X | 相當安逸（鄭重強調） |
| 巴適得很 | 「非常舒服」 |
| 扎實 X | 扎實好吃 |
| 莫得辦法 | 沒辦法 |
| 哦豁不得了 | 糟糕了 |
| 搞快點 | 趕緊 |
| 緊到 X | 一直在 X |
| 將就 | 湊合 |
| 嘿（嗨） | 強化 |

#### V5. 動詞詞替換 [Hard, Light+]

Routinely swap Putonghua verbs for 川渝 equivalents.

| 普通話 | 川渝 |
|---|---|
| 看 | 瞅、瞄 |
| 走 | 走、跑路 |
| 坐 | 杵、坐到 |
| 站 | 站起 / 杵到 |
| 拿 | 拿起、揣 |
| 給 | 拿給、捎 |
| 害怕 | 怕、慫 |
| 罵 | 凶、剋 |
| 吃 | 吃、整 |
| 做 | 搞、整、弄 |
| 想 | 想、捉摸 |
| 不知道 | 莫曉得、不曉得 |

---

### Particle Patterns（語尾助詞）

四川話 particles ride **on top of** sentences in a denser stack than Putonghua,
each with a distinct pragmatic function. Combination rule: usually one
particle per sentence; 「嘛」 may chain after 「噻」 / 「撒」 for emphasis.

#### P1. 嘛 — 緩和 / 理所當然 / 軟性催促 [Hard, Light+]

The most ubiquitous 川渝 particle. Softens commands, marks "that's obvious",
or gentle complaint.

> **Reasoning-evident:** 就是這個道理嘛。
>
> **Soft urging:** 你來嘛。
>
> **Mild complaint:** 莫亂說嘛！

#### P2. 噻 / 撒 — 肯定 / 祈使 [Hard, Light+]

Marks confirmation or imperative — closer to Putonghua "啊" but with川渝
edge. 撒 is a common written variant.

> **Confirmation:** 就是這樣噻。
>
> **Imperative:** 過來噻！
>
> **Variant:** 拿給我撒。

#### P3. 嘞 — 完成 / 變化 [Hard, Light+]

Marks change of state or completion, with 川渝 cadence. Roughly = 了 + 啦.

> **Completion:** 我吃老嘞。
>
> **State-change:** 天黑嘞。
>
> **Decision:** 算嘞算嘞。

#### P4. 哈 — 確認 / 友善提醒 [Hard, Light+]

Seeks light agreement or marks friendly reminder. Slightly warmer than 噻.

> **Agreement-seek:** 巴適得很哈？
>
> **Reminder:** 路上小心哈。
>
> **Confirmation:** 就這樣哈。

#### P5. 喲 / 哦 — 驚訝 / 恍然 [Soft, Medium+]

Marks discovery, surprise, mild alarm.

> **Discovery:** 還真有兩下子喲。
>
> **Alarm:** 哦豁，遭嘞！

#### P6. 嗦 / 唦 — 詢問 / 推斷 [Soft, Medium+]

Roughly = "is that so?" / asking to confirm an inference.

> **Inferential ask:** 你不去嗦？
>
> **Confirming inference:** 原來如此嗦。

---

### Structure Patterns（結構模式）

#### S1. 短句 + 反問 [Hard, Light+]

四川話 rhythm is short, fast, blunt. Long subordinated periods are not 四川話
voice; break them down. Rhetorical 反問 is the daily structure of confrontation
or surprise.

| 反問套式 | 場合 |
|---|---|
| 你說啥子？ | 沒聽清 / 不爽 |
| 咋的嘛？ | 挑釁 / 不服 |
| 哪個說的？ | 質疑來源 |
| 你龜兒搞啥子？ | 強烈不滿 |
| 我搞錯了嗦？ | 自我懷疑 |

> **Standard:** 我並不認為這件事是這樣的。
>
> **Sichuan:** 哪個說是這樣？我看莫得這回事。

#### S2. 自嘲與江湖氣 [Hard, Medium+]

The 川渝 voice is willing to laugh at itself. Self-deprecation through
「老子」 over-claims ("老子今天又把車鑰匙弄丟嘞") balanced by mock-bragging
("老子這手藝，巴適得很") is the texture of川劇丑角 and《讓子彈飛》張麻子
alike. Use it to de-fuse heavy emotions.

> **Tense:** 我又把事情搞砸了。
>
> **川渝 self-mock:** 老子又把這事兒搞砸嘞，瓜娃子一個。

#### S3. 擬聲與動感 [Soft, Medium+]

四川話 carries strong onomatopoeia and motion-words.

| 擬聲 / 動感 | 場合 |
|---|---|
| 撲哧 | 笑出聲 |
| 啪嗒 | 物件落地 |
| 嘩啦 | 水聲 / 倒塌 |
| 咕嚕咕嚕 | 火鍋翻滾 |
| 唏哩呼嚕 | 吃麵聲 |
| 咔 | 突然停 |
| 咚咚咚 | 腳步聲 / 心跳 |

#### S4. 寒暄與起頭 [Soft, Medium+]

| 開場 | 場合 |
|---|---|
| 哎喲 | 驚嘆、不滿 |
| 哦豁 | 糟了、突發 |
| 嘿 | 招呼 |
| 你龜兒 | 戲謔招呼 |
| 走嘛 | 邀約 |
| 來來來 | 招呼入座 |

### Meta Patterns（後設規則）

#### M1. 全形標點零違規 [Hard, Light+]

CJK 文本中所有標點一律全形。**ASCII 半形 `, ; : ? !` 在 CJK 字之間出現一律是 bug**，必須換成全形 `，；：？！`。對照表：

| 半形（禁） | 全形（用） | Unicode |
|---|---|---|
| `,` | `，` | U+FF0C |
| `;` | `；` | U+FF1B |
| `:` | `：` | U+FF1A |
| `?` | `？` | U+FF1F |
| `!` | `！` | U+FF01 |
| `(` `)` | `（` `）` | U+FF08 / U+FF09 |

破折號用兩個全形「—」連寫成「——」；引號用「」/『』；句號用「。」；全形標點與 CJK 之間零空格。

**寫完後必跑自檢指令**（指令名留作機械驗證，不可省略）：

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

---

## Step 3: Produce Sichuan Mandarin Output

Apply the checklist to transform the entire text. Aim for a natural 川渝 voice
at the chosen intensity. Always check the soul clause first — if the output
reads as Putonghua with a few swaps, push 莫/莫得， particles, and 江湖 cadence
harder.

### Intensity Levels

Each rule is tagged with its minimum intensity (e.g., `[Hard, Light+]` = active
from Light up; `[Soft, Heavy]` = mainly Heavy).

| Level | Active Rules | Effect | Marker Density |
|---|---|---|---|
| **Light** | G1-G4, G6, V1, V3, V5, P1-P4, S1, S4. No 老子/龜兒， no 川劇丑角 cadence. | 普通話 backbone with occasional 川渝 flavor — 巴適/莫得/嘛/哈/搞快點 sprinkled. Like a Sichuanese speaker writing a slightly dressed-up WeChat post. | 5-6 sentences carry 1-2 markers |
| **Medium** (default) | Light + G5, G7 (selective), V2, V4, P5-P6, S2-S3. 老子/龜兒 used in self-reference and friendly banter. | Clearly 川渝 — signature words, particles, blunt cadence, mild self-mockery. Like a 重慶 茶館 conversation transcribed. | every 2-3 sentences carry ≥1 marker |
| **Heavy** | All rules including G7 free, S2 full 江湖 cadence, dense particles, 川劇丑角 self-mockery. | Heavy 川渝 — 張麻子-grade 江湖 voice, every line salted, rhetorical 反問 frequent, 老子/龜兒 freely used. | every 1-2 sentences carry ≥1 marker, ≥2 in dialogue |

If the user doesn't specify, use **Medium**.

### Input-Specific Handling

**Mandarin input → Sichuan Mandarin:**

1. Swap 沒/沒有 → 莫/莫得 systematically (G1).
2. Swap 什麼/怎麼/誰 → 啥子/咋個/哪個 (G4).
3. Replace key verbs with 搞/整 family (G3) and V5 swaps.
4. Add particles 嘛/噻/嘞/哈/撒 (P1-P4) where pragmatic meaning calls.
5. Add 兒 化 in legitimate slots only (G2).
6. Inject signature lexicon (V1, V4) — aim for ≥3 markers per paragraph at
   Medium+.
7. Apply intensifier patterns (G6).
8. At Medium+, allow 老子/龜兒 in self-reference / friendly banter (G7);
   at Heavy, freely.
9. Break long sentences into short blunt clauses; insert rhetorical 反問
   where it fits (S1, S2).
10. Verify the **soul clause** — if reading the output back doesn't sound
    like 川渝 江湖+幽默 voice, push harder on particles, 莫得 negation, and
    自嘲 cadence.

**Non-Mandarin input → Sichuan Mandarin:**

1. Translate to Standard Written Chinese first.
2. Apply Sichuan transforms as above.

---

## Step 4: Output

1. **File output:** Save to `_sichuan` suffix (e.g., `article.md` →
   `article_sichuan.md`). If no file was provided, output directly in
   conversation.
2. **Show 3-5 representative sentence pairs** comparing Original and Sichuan
   Mandarin.
3. **List applied patterns:** Note which major pattern groups (G/V/P/S) were
   most active.
4. **Glossary:** List signature 川渝 terms used, with Putonghua equivalents.

---

## Anti-patterns（常見失敗模式）

寫完一稿、自檢之前，先掃一眼這條最容易踩的坑：

1. **半形標點混入** — 輸出時把 `,;:?!` 打成 ASCII 半形而非全形 `，；：？！`。
   常見原因是 IME 切換失誤或從英文 prompt 複製字串。M1 已明文要求全形；
   寫完務必跑 M1 自檢指令，計數歸零才算交付。

---

## Important Notes

- This is a **stylistic transformation tool** for creative, educational, and
  cultural purposes.
- 四川話 is a **legitimate Mandarin variety** （西南官話 成渝片） covering
  Sichuan, Chongqing, and adjacent areas of Yunnan, Guizhou, Hubei, Shaanxi —
  ~120 million speakers, one of the largest Mandarin sub-dialects. Treat it
  with linguistic respect.
- **Linguistic background.** Phonology: 入聲 collapsed into 陽平 (the
  innovative trait that distinguishes 西南官話 from northern Mandarin); 兒
  化 limited to 4 韻尾 ([ɚ][iɚ][uɚ][yɚ]) vs Beijing's 26; 平翹 distinction
  largely absent. Lexicon: a substantial layer of words are local
  (巴適/搞快點/莫得) rather than just pronunciation variants of standard
  Mandarin.
- **重慶 vs 成都 micro-difference.** Both belong to 成渝片 and are mutually
  intelligible, but the registers differ slightly: Chongqing leans harder
  / sharper / more 江湖, Chengdu softer / more leisurely / more 茶館-style.
  Particles 嘛/噻 are more frequent in Chengdu; 老子/龜兒 land more
  naturally in Chongqing-flavored speech. The skill does not enforce a
  split — choose register by content, not by city tag.
- **Avoid stereotype.** Do NOT lean on "lazy / mahjong-addicted / hotpot-
  obsessed" tropes when characterizing speakers or scenarios. The dialect's
  lexicon includes 火鍋 / 茶館 / 川劇 because those are real cultural anchors,
  not because Sichuanese identity reduces to leisure. The voice is 江湖+幽默
  — direct, self-aware, willing to laugh at fate — not idleness.
- **「老子」 and 「龜兒」 are calibrated by context.** Among friends they are
  warm or playful; in confrontation they sharpen into curse. Don't dump them
  into Light register — they signal a step toward 江湖 cadence.
- **「莫得」 ≠ random 沒.** 莫 is the negator; 莫得 specifically means 沒有
  (don't have). 莫得辦法 = no way out, 莫法 = abbreviated form. Use the
  right one.
- **High-frequency markers also include**: 要得 (good / ok / agreed —
  the signature Sichuan affirmative), 嘎嘎 (meat, child-talk), 扯把子
  (chat / gossip / bullshit). Add these to the active vocabulary in
  Medium/Heavy outputs.
- **「兒」化 is restricted.** Only 4 韻尾 in 四川話 vs. 26 in northern
  Mandarin. Add 兒 to place names, small objects, playful adjectives, kinship
  terms — not to abstract nouns or actions.
- **Particles are not random filler.** Each carries function:
  - 嘛 = soft / obvious
  - 噻 / 撒 = confirmation / imperative
  - 嘞 = completion / change of state
  - 哈 = friendly agreement-seek
  - 喲 / 哦 = surprise / discovery
- **Formal / classical input produces absurd output.** A legal contract or
  classical poem rendered into 四川話 will be comical, not useful — warn
  the user before transforming.
- **Simplified vs. traditional.** This skill follows the input character set
  by default — 繁 in, 繁 out; 簡 in, 簡 out. Mainland 四川話 writing is
  typically simplified; if the user wants authentic mainland feel, ask.
- When in doubt, think: "Would this come out of a Chengdu 茶館 regular's
  mouth, or a Chongqing 火鍋 boss's, or 張麻子's in《讓子彈飛》?" That's
  the register we target.
