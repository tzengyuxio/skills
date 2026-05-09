---
name: written-cantonese
description: >
  Transform text into full written Cantonese （粵語書面語 / 廣東話書面化） — not
  Standard Written Chinese with Hong Kong vocabulary, but Cantonese all the way
  down: function words （係 / 唔 / 嘅 / 咗 / 佢 / 喺）, Cantonese syntax
  （adverb-after-verb 行先 / 食多啲， post-verbal completives 食晒 / 行咗，
  direct-then-indirect double objects 畀錢你）, dense sentence-final particles
  （喎 / 啦 / 㗎 / 咩 / 咯 / 啩 / 嘛 / 咧）, and at Heavy intensity LIHKG /
  連登 web register （巴打 / 絲打 / on9 / mk）. Three intensity levels from
  light particle-and-pronoun swap to full LIHKG-style 連登體.
  Useful for creative writing, dialogue scripting, web-forum simulation, language
  education, and cultural appreciation.
  Triggers on "/written-cantonese", "改寫成粵語書面", "改寫成廣東話書面",
  "寫成粵語", "寫成連登體", "translate to written cantonese", "make it cantonese
  written", "粵語書面化", "廣東話書面化", "連登", "LIHKG", "周星馳粵語對白".
argument-hint: [file-path]
allowed-tools: Read, Write, Edit, Glob
---

# Written Cantonese — 粵語書面語 / 廣東話書面化

Transform text into **full written Cantonese** — the written representation of
廣東話 / 粵語 as actually spoken, with Cantonese function words, Cantonese
syntax, and Cantonese sentence-final particles throughout. The result should
read like a TVB drama subtitle, a 周星馳 film line, a 連登 (LIHKG) thread, an
Apple Daily gossip column, or a WhatsApp message between Hong Kong friends —
not a translation, but **Cantonese committing itself to the page**.

## Soul clause

**Full written Cantonese means the syntax is also Cantonese, not just the
vocabulary.** The text must include core Cantonese function words
（係 / 唔 / 嘅 / 咗 / 佢 / 喺）, Cantonese sentence-final particles
（喎 / 啦 / 㗎 / 咩 / 咯 / 嘅 / 啩 / 嘛 / 咧）, and Cantonese word order
（adverb-after-verb 行先 / 食多啲， post-verbal completive 食晒 / 行咗，
direct-then-indirect double objects 畀錢你）. A text that swaps a few HK
vocabulary items but keeps Mandarin syntax is **not** written Cantonese.

## Background — Orthographic context

- **HKSCS （香港增補字符集）** — first published 1999, latest revision 2016.
  Around 4,700 characters covering Cantonese-specific forms （啲 / 嘢 / 喺 / 嘅
  / 嗰 / 嚟 / 喎 / 㗎 etc.) plus alternate forms used in HK personal and place
  names. Full Unicode coverage from CJK Unified Ideographs Extension B onward.
- **教育局 / Education Bureau** — Hong Kong government policy treats 書面語
  (Standard Written Chinese with Mandarin grammar) as the medium of education,
  legislation, and official documents; Cantonese is the medium of instruction
  for spoken delivery in primary/secondary schools but not the written
  standard. Written Cantonese has no government-issued orthographic standard
  comparable to Taiwan's 教育部 700-字詞推薦用字 for Hokkien.
- **Apple Daily / TVB / 連登 LIHKG** — popular media, gossip columns, drama
  subtitles, and online forums use written Cantonese extensively. This is the
  living orthographic norm: deciding 「我哋 vs 我們」、「冇 vs 沒」、「點解 vs
  為何」 happens by community usage rather than official decree.
- **Formal vs casual register** — Hong Kong legislation, court documents, news
  reports, and academic writing use Standard Written Chinese with Mandarin
  grammar even when the intended reader is a Cantonese speaker. Written
  Cantonese is the **casual / popular / dialogue** register, not a replacement
  for the formal register.

## Arguments

- `$0` — (Optional) Path to a markdown or text file. If omitted, find the most
  recent text in conversation context or ask the user.

## Step 1: Load the Text

- If `$0` is provided, read the file.
- Input can be **Mandarin / Standard Written Chinese** (rewrite as written
  Cantonese), **English / any language** (translate to written Cantonese), or
  already partial Cantonese (normalise to chosen intensity).

## Step 2: Apply Written Cantonese Patterns

The checklist below has 21 items in four categories: **Grammar**, **Vocabulary**,
**Structure**, **Meta**. Each rule is tagged `Hard` (required) or `Soft`
(recommended), plus minimum intensity (`Light+` / `Medium+` / `Heavy`).

The **soul clause** is enforced as a Hard rule across G1, G6, S1: at every
intensity, function-word swap （係 / 唔 / 嘅 / 咗 / 佢 / 喺）, Cantonese
sentence-final particles, and at least one Cantonese-syntactic feature
(adverb-after-verb, post-verbal completive, or direct-then-indirect double
object) must appear.

---

### Grammar 語法

#### G1. 核心虛詞替換 [Hard, Light+]

The non-negotiable backbone of written Cantonese. Every Mandarin function word
in this table swaps to its Cantonese counterpart at every intensity. A text
that keeps 是 / 不 / 的 / 了 / 他 is by definition not written Cantonese.

| 普通話 | 粵語書面 | 讀音（粵拼） | 說明 |
|---|---|---|---|
| 是 | 係 | hai6 | 判斷句必用 |
| 不 | 唔 | m4 | 一般否定 |
| 沒（有） | 冇 | mou5 | 存在 / 完成否定 |
| 的 | 嘅 | ge3 | 屬性助詞 |
| 了 | 咗 | zo2 | 完成貌 |
| 他 / 她 | 佢 | keoi5 | 不分性別 |
| 在 | 喺 | hai2 | 處所介詞 |
| 這 / 這個 | 呢 / 呢個 | ni1 | 近指 |
| 那 / 那個 | 嗰 / 嗰個 | go2 | 遠指 |
| 一些 | 啲 | di1 | 量詞 / 複數標記 |
| 來 | 嚟 | lai4 | 趨向 |
| 給 | 畀 | bei2 | 與格 / 被動 |
| 們 | 哋 | dei6 | 我哋 / 你哋 / 佢哋 |
| 和 | 同 / 同埋 | tung4 | 並列 |
| 也 | 都 | dou1 | 同 |
| 很 | 好 | hou2 | 程度副詞 |
| 怎麼 / 為什麼 | 點 / 點解 | dim2 / dim2 gaai2 | 疑問 |

#### G2. 副詞後置 [Hard, Light+]

Cantonese routinely places adverbs *after* the verb where Mandarin places them
before. This is one of the clearest syntactic markers and must appear.

| 普通話 | 粵語 | 字面結構 |
|---|---|---|
| 你先走 | 你行先 | V + ADV |
| 多吃一點 | 食多啲 | V + 多 + 啲 |
| 你再來一次 | 你嚟多次 | V + 多 + 次 |
| 我先走了 | 我走先 | V + ADV |
| 給我看看 | 畀我睇下 | V + 下 |

> **普通話：** 你先吃，我等一下再來。
>
> **粵語：** 你食先啦，我遲啲先嚟。

#### G3. 動補後置 / 完成貌 [Hard, Medium+]

Post-verbal completive markers （晒 / 咗 / 緊 / 過 / 落 / 開）attach directly to
the verb, expressing completion, progression, experience, or continuation.

| 標記 | 功能 | 例 |
|---|---|---|
| 咗 | 完成貌（=了） | 食咗飯 |
| 晒 | 全部 / 完盡 | 食晒 / 用晒 |
| 緊 | 進行貌（=正在） | 食緊飯 |
| 過 | 經驗 | 食過日本嘢 |
| 開 | 持續 / 一向 | 做開呢行 |
| 落 | 持續向下 / 入 | 食落 / 寫落 |
| 埋 | 一併 / 連帶 | 食埋呢碗 |

> **普通話：** 我已經吃完飯了。
>
> **粵語：** 我食晒飯喇。 / 我食咗飯喇。

#### G4. 雙賓語語序 [Hard, Medium+]

Cantonese double-object order is **direct-then-indirect**, opposite of
Mandarin's indirect-then-direct.

| 普通話 | 粵語 | 結構 |
|---|---|---|
| 他給我一本書 | 佢畀本書我 | V + 直接賓 + 間接賓 |
| 我給他錢 | 我畀錢佢 | V + 錢 + 佢 |
| 老師教我們粵語 | 老師教粵語我哋 | V + 內容 + 對象 |

The Mandarin order （我畀佢錢）is also acceptable in casual Cantonese, but
the canonical, distinctively-Cantonese form is direct-then-indirect — use it
at least once when the rule applies.

#### G5. 句末助詞群 [Hard, Light+]

The respiratory rhythm of Cantonese. Without these the text reads as
Mandarin-with-Cantonese-vocabulary, not as Cantonese.

| 助詞 | 粵拼 | 功能 |
|---|---|---|
| 啦 | laa1 | 緩和 / 催促 / 顯然 |
| 喎 | wo3 | 傳述 / 提醒 / 訝異 |
| 㗎 | gaa3 | 強調 / 確認 |
| 咩 | me1 | 反問 / 疑惑（「真係咩？」） |
| 咯 | lo3 / lo1 | 接受 / 認命 / 無奈 |
| 嘅 | ge3 | 句末強調 |
| 啩 | gwaa3 | 推測（「應該係啩」） |
| 嘛 | maa3 | 顯然 / 提示 |
| 咧 | le5 | 軟化 / 撒嬌 |
| 啊 | aa3 | 開放陳述 |
| 㗎啦 | gaa3 laa1 | 強調 + 緩和 |
| 咯喎 | lo3 wo3 | 領悟 + 訝異 |

Use **at least one particle every 2-3 sentences** at Medium+; sparser at Light.

#### G6. 處置 / 被動 [Soft, Medium+]

- 處置：用 **將 + NP + V**（粵語也用，但比起普通話頻率較低；常用「攞 NP V」）
- 被動：用 **畀 + 施事 + V**（畀 = 給 / 被）

> **普通話：** 他被老闆罵了。
>
> **粵語：** 佢畀老闆鬧咗。

#### G7. 反問 / 疑問句式 [Hard, Medium+]

| 結構 | 功能 | 例 |
|---|---|---|
| V 唔 V | 是非問 | 食唔食？係咪？去唔去？ |
| 係咪 | 是不是 | 你係咪佢個朋友？ |
| 點解 | 為什麼 | 點解你今日咁早返？ |
| 邊個 / 邊度 / 幾時 | 誰 / 哪 / 何時 | 邊個話㗎？喺邊度？ |
| ...咩 | 反詰 | 你唔知咩？真係咩？ |
| ...啊嘛 | 顯然反詰 | 食飯啊嘛 |

---

### Vocabulary 詞彙

#### V1. 核心粵語動詞 [Hard, Light+]

These single-character verbs replace bisyllabic or different Mandarin forms.
They are the most frequent everyday Cantonese vocabulary.

| 粵語 | 普通話 | 粵拼 |
|---|---|---|
| 食 | 吃 | sik6 |
| 飲 | 喝 | jam2 |
| 睇 | 看 | tai2 |
| 瞓 | 睡 | fan3 |
| 行 | 走 | haang4 |
| 走 | 跑 / 離開 | zau2 |
| 企 | 站 | kei5 |
| 講 | 說 | gong2 |
| 攞 | 拿 | lo2 |
| 揾 | 找 | wan2 |
| 知 | 知道 | zi1 |
| 識 | 認識 / 會 | sik1 |
| 鍾意 | 喜歡 | zung1 ji3 |
| 中意 | 喜歡（變體） | zung1 ji3 |

#### V2. 文化詞 / 港式生活詞 [Hard, Light+]

| 粵語 | 普通話 |
|---|---|
| 屋企 | 家 |
| 茶餐廳 | 港式餐館 |
| 絲襪奶茶 | 港式奶茶 |
| 菠蘿油 | （港式麵包） |
| 街市 | 菜市場 |
| 屋邨 | 公屋社區 |
| 巴士 | 公車 |
| 的士 | 計程車 |
| 銀包 | 錢包 |
| 雪櫃 | 冰箱 |
| 鎖匙 | 鑰匙 |
| 遮 | 雨傘 |
| 老婆 / 老公 | 妻 / 夫（口語） |
| 阿婆 / 阿伯 | 老太太 / 老先生 |

#### V3. 程度 / 數量詞 [Hard, Medium+]

| 粵語 | 普通話 |
|---|---|
| 好（X） | 很（X） |
| 好鬼（X） | 非常 |
| 勁 / 勁過 | 厲害 / 強過 |
| 正 / 好正 | 棒 |
| 靚 | 漂亮 / 好 |
| 慘 / 好慘 | 可憐 / 糟糕 |
| 抵 / 好抵 | 划算 |
| 啱 / 啱啱 | 對 / 剛剛 |

#### V4. LIHKG / 連登 / 網絡用語 [Hard, Heavy]

Heavy mode opens up the 連登 web register. These are **internet vocabulary**,
not standard Cantonese — use only when the user wants the LIHKG / 高登 /
forum flavour.

| 詞 | 意思 / 出處 |
|---|---|
| 巴打 | brother（連登男性網友） |
| 絲打 | sister（連登女性網友） |
| 連登仔 | LIHKG 男用戶 |
| on9 / on99 | 戇鳩（粗口諧音 → 笨） |
| mk | 旺角風格的青少年（貶） |
| lm | 老母（粗，慎用） |
| 廢青 | 無所事事的青年 |
| 港豬 | 政治冷漠的港人（慎用，可能冒犯） |
| 黃絲 / 藍絲 | 政治立場代稱（**避免實質立場使用**） |
| 高登 | 較舊的香港論壇 |
| 食花生 | 看戲 / 看熱鬧 |
| 冇眼睇 | 看不下去 |
| 屌 / D | 強烈情緒（粗，慎用） |

**政治詞中性化**：黃絲 / 藍絲 / 五大訴求 / 國安法 等政治標籤詞**避免實質
立場使用**。如必須出現，僅作為「香港網絡語體」的詞彙存在標記，不附加
立場評斷；改寫範例優先選擇非政治題材。

#### V5. 港式音譯 / 借詞 [Soft, Medium+]

| 粵語 | 原文 |
|---|---|
| 朱古力 | chocolate |
| 三文治 | sandwich |
| 多士 | toast |
| 梳化 | sofa |
| 士多 | store |
| 啤梨 | pear |
| 芝士 | cheese |
| 忌廉 | cream |

#### V6. 中英 code-mixing [Hard, Medium+]

Cantonese-speaking Hong Kong is heavily code-mixing; written Cantonese reflects
this. Insert English words for nouns (project / meeting / email / office),
verbs (check / send / book / confirm / send), and evaluations (OK / fine /
chill / cool). Heavy mode goes denser, every 2-3 sentences.

> 我而家喺 office 開緊個 meeting，send 完 email 再 call 你啦。

---

### Structure 結構 / 體裁

#### S1. 至少一處非典型粵語語序 [Hard, Light+]

Every output must contain at least one syntactic feature drawn from G2-G4
(adverb-after-verb, post-verbal completive 晒 / 咗 / 緊， or
direct-then-indirect double object). A text that only swaps function words
without altering syntax fails the soul clause.

#### S2. 粵字密度 [Hard, Light+]

| 強度 | 粵字密度 | 說明 |
|---|---|---|
| Light | 每段 5-8 個核心粵字 | 係 / 唔 / 嘅 / 佢 / 嗰 / 啲 等 |
| Medium | 每句平均 2-3 個粵字 | 加上 喺 / 咗 / 哋 / 點 / 嚟 / 食 / 睇 |
| Heavy | 每句多個粵字 | 加上 連登 V4、密集句末助詞、code-mixing |

#### S3. 量詞特化 [Soft, Medium+]

| 粵式量詞 | 普通話 |
|---|---|
| 一隻（歌 / 貓） | 一首 / 一隻 |
| 一部（戲 / 車） | 一部 / 一輛 |
| 一啲 | 一些 |
| 一齣 | 一場 / 一部 |
| 一間（屋 / 舖） | 一間 / 一棟 |
| 一舊 | 一塊 / 一份 |
| 一樖（樹） | 一棵 |
| 一條（友 / 人） | 一個（人） |

#### S4. 連登 / 對白 文體標誌 [Soft, Heavy]

Heavy mode can adopt 連登 thread conventions: short paragraphs, ALL-CAPS English
inserts (LOL / WTF / TBH), Cantonese-romanization slips (lm / on9 / hi auntie
類混入）、emoji 與顏文字、開場語「點呀大家」「巴打 / 絲打」對讀者寒暄。

---

### Meta 元規則

#### M1. 不是港式中文 [Hard, Light+]

Written Cantonese is **not** Hong Kong Chinese with Mandarin syntax. If the
output keeps 是 / 不 / 的 / 了 / 他 throughout while only sprinkling 巴士 /
雪櫃 / 三文治， the result fails this skill — that is Standard Written Chinese
in HK vocabulary, not 粵語書面語. The function-word swap (G1) must apply at
**every** intensity, including Light.

#### M2. 適用語境 [Hard, Light+]

Written Cantonese suits casual register: dialogue, web forums, drama subtitles,
gossip columns, song lyrics, advertising, social media. It does **not** suit
formal register: legislation, court documents, academic theses, government
notices, news reports of record. If the input is a legal contract or
constitutional preamble, warn the user before transforming.

#### M3. 政治詞中性化 [Hard, Light+]

Political terms （黃絲 / 藍絲 / 五大訴求 / 國安法 / 反送中 / 港獨 / 大灣區）
must be neutralised: avoid producing them in demos; if they appear in input,
preserve them as-is without adding partisan colour; never invent new political
content. Choose non-political source material for examples.

#### M4. 朗讀檢查 [Hard, Light+]

Read the output aloud as Cantonese (silent or vocalised). If a sentence cannot
be pronounced naturally in Cantonese without re-translating in your head, that
sentence is still Mandarin — fix it.

#### M5. 不嘲弄香港文化 [Hard, Light+]

The goal is authentic written Cantonese as actually used by Hong Kong writers,
forum posters, and screenwriters — not exaggerated 「港燦」stereotype, not
mocking imitation, not tone-deaf cultural appropriation. Treat 粵語 as a
language with its own literary tradition （黃霑、林夕 歌詞；金庸 / 倪匡 早期港
報連載；周星馳 對白；連登 / Apple Daily 文體）.

#### M6. 全形標點零違規 [Hard, Light+]

CJK 段所有標點一律全形。**ASCII 半形 `, ; : ? !` 在 CJK 字之間出現一律是 bug**，必須換成全形 `，；：？！`。對照表：

| 半形（禁，當夾在 CJK 字之間時） | 全形（用） | Unicode |
|---|---|---|
| `,` | `，` | U+FF0C |
| `;` | `；` | U+FF1B |
| `:` | `：` | U+FF1A |
| `?` | `？` | U+FF1F |
| `!` | `！` | U+FF01 |
| `(` `)` | `（` `）` | U+FF08 / U+FF09 |

破折號用兩個全形「—」連寫成「——」；引號用「」/『』；句號用「。」；全形標點與 CJK 之間零空格。**例外**：英文插入照英文慣例（Step 8 標點清理已說明）；自檢規則只檢「CJK 字相鄰的 ASCII 半形標點」，不誤抓英文段內。

**寫完後必跑自檢指令**（指令名留作機械驗證，不可省略）：

```bash
python3 -c "
import re, sys
text = open(sys.argv[1]).read()
bad = re.findall(r'[一-鿿㐀-䶿][,;:?!][一-鿿㐀-䶿]', text)
print(f'half-width punct between CJK: {len(bad)}')
for b in bad[:5]: print(repr(b))
" 輸出檔.md
```

結果必須為 `0`。非 0 表示輸出時混入了 ASCII 半形於 CJK 字之間，逐字替換後重跑，直到歸零才算交付。

---

## Step 3: Choose Intensity & Produce Output

| 強度 | 特徵 | 典型場景 | 範例片段 |
|---|---|---|---|
| **Light** | G1 全用（係 / 唔 / 嘅 / 佢 / 嗰 / 啲），G2 副詞後置至少 1 處，G5 句末助詞偶用，V1 核心動詞替換，無 V4 連登詞，無 V6 dense code-mixing | TVB 字幕 / 普及型粵語對白 / 報章引述對話 | 「佢話聽日嚟我屋企食飯，我問佢點解咁急。」 |
| **Medium**（預設） | Light + G3 完成貌（咗 / 晒 / 緊）+ G4 雙賓語 + G7 反問（係咪 / 點解）+ V3 程度詞 + V5 港式音譯 + V6 code-mixing 中度 + S3 量詞特化 + 句末助詞密集 | Apple Daily 專欄 / WhatsApp 聊天 / 日常 blog | 「我頭先 send 咗個 email 畀佢，仲未 reply 喎。」 |
| **Heavy** | Medium + V4 連登詞 + S4 連登文體標誌 + V6 code-mixing 密集 + 顏文字 / 大寫英文插入 | LIHKG / 連登貼文 / 高登 / 香港討論區 / 周星馳式插科打諢 | 「巴打你 on9 㗎？個 project 都未 confirm，仲喺度 send email？」 |

If the user does not specify, default to **Medium**.

### Input-Specific Handling

**Mandarin / 標準書面中文 → 粵語書面：**
1. 全篇替換 G1 核心虛詞（係 / 唔 / 嘅 / 咗 / 佢 / 喺 / 呢 / 嗰 / 啲 / 嚟 / 畀 / 哋 / 同 / 都 / 好 / 點解）
2. 動詞替換 V1（食 / 飲 / 睇 / 瞓 / 行 / 企 / 講 / 攞 / 揾）
3. 句法粵語化：副詞後置（G2）至少 1 處；Medium+ 加完成貌（G3）；Medium+ 雙賓語（G4）至少 1 處
4. 句末助詞（G5）：每 2-3 句加一個（喎 / 啦 / 㗎 / 咩 / 咯 / 嘅）
5. 文化詞替換 V2（屋企 / 銀包 / 鎖匙 / 巴士 / 雪櫃）
6. 依強度加 V4（連登）/ V5（音譯）/ V6（code-mixing）
7. 朗讀檢查（M4）：不能粵語自然念出的句子，重改
8. 標點清理：CJK 段全形，英文插入照英文慣例
9. 政治詞檢查（M3）：避免具體立場

**英文 / 其他語言 → 粵語書面：**
1. 先翻為自然粵語口語句法（不是標準書面中文）
2. 套用上述 1–9 步

---

## Step 4: Output

1. **檔案輸出**：另存為 `_cantonese` 後綴（`article.md` →
   `article_cantonese.md`）；無檔案則直接於對話輸出。
2. **3-5 組對照句**：原文 vs 粵語書面對比，並標出觸發的 G / V / S / M 條目。
3. **靈魂條款達標檢核**：列出 G1（核心虛詞）、G2 / G3 / G4（粵語語序）、
   G5（句末助詞）三組是否都至少出現一處。
4. **詞彙表**：列出本篇出現的核心粵字、句末助詞、文化詞，附普通話對應。

---

## Anti-patterns（常見失敗模式）

寫完一稿、自檢之前，先掃一眼這條最容易踩的坑：

1. **半形標點混入 CJK 字之間** — 把粵語句的逗號 / 句號 / 問號等打成 ASCII
   半形而非全形。常見原因是 IME 切換失誤或從英文 prompt 複製字串。英文插入
   段的標點不算違規。M6 已明文要求全形；寫完務必跑 M6 自檢指令，計數歸零才
   算交付。

---

## Important Notes

- 這是一個**語體轉換工具**，用於創作、教育、文化欣賞與對白寫作。
- 粵語 / 廣東話是一個**有完整書面傳統**的漢語語言，本 skill 視之為語言學
  現象，不採政治論述。
- **句法走粵語**是底線。把標準中文句子的詞替成粵字而句法不動，產生的是
  「粵語讀音的中文」，不是粵語書面 — 必須改造詞序與功能詞。
- **強度一致性**比強度激進度更重要。Light 與 Heavy 在同一篇內混用會嚴重
  損害可讀性。
- HKSCS 並非對所有粵字都有定字 — 部分本字仍有用字爭議（如「揾 vs 搵」、
  「冚 vs 蓋」），本 skill 採通行寫法（多數港報及 Apple Daily 慣例），不
  採學院本字復原立場。
- 政治敏感詞處理見 M3。改寫政治題材輸入時，保留原文用詞但不加立場色彩；
  範例選材避開政治。
- 若輸入為法律條文、政府公告、學術論文，請先告知使用者：產出會讀來
  違和或滑稽，因為這類文體在書寫傳統中本就用標準書面中文，不用粵語。
- 朗讀檢查（M4）是最後一關。寫完用粵語默讀一遍，每個句末助詞、每個動補
  後置、每個雙賓語都應自然落地。
