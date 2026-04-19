---
name: taiwan-mandarin
description: >
  Transform text into Taiwan Mandarin (台灣國語) — a sociolect of Mandarin shaped by
  prolonged contact with Taiwanese Hokkien, featuring Hokkien/Japanese loanwords,
  phonologically-motivated respellings (偶/粉/素/降), sentence-final particles (啦/喔/齁/耶),
  and BBS-era net culture spellings (注音文 such as ㄉ/ㄇ/ㄅ/3Q).
  Applies a checklist covering grammar, particles, vocabulary, and structure, with
  three intensity levels from light colloquial chat to heavy 2000s netizen style.
  Useful for creative writing, cultural appreciation, language education, or humor.
  Triggers on "/taiwan-mandarin", "寫成台灣國語", "台灣國語化", "翻成台灣國語",
  "translate to taiwan mandarin", "make it taiwan mandarin", "台灣腔", "台式中文".
argument-hint: [file-path]
allowed-tools: Read, Write, Edit, Glob
---

# Taiwan Mandarin — 台灣國語

Transform text into Taiwan Mandarin (台灣國語) — a living sociolect of Mandarin shaped by
decades of contact with Taiwanese Hokkien. The result should read like an authentic
Taiwanese speaker typing casually on LINE, PTT, or 無名小站 — warm, colloquial, and
unmistakably local.

Taiwan Mandarin is NOT broken Mandarin or a caricature. It is a **systematic variety**
with its own phonology (often reflected in spelling), lexicon, and pragmatic particle
system. Every feature reflects real contact patterns between Mandarin and Taiwanese
Hokkien, sometimes layered with Japanese loanwords and BBS-era internet culture.

This skill targets the **written representation** of Taiwan Mandarin — not the oral
phonetics, but the ways those phonetic and lexical features surface in casual text.

## Arguments

- `$0` — (Optional) Path to a markdown or text file. If omitted, ask for inline text or
  find the most recent text in conversation context.

## Step 1: Load the Text

- If `$0` is provided, read the file.
- If no argument, find the most recent text in the conversation, or ask the user.
- The input can be **Mandarin Chinese** (rewrite as Taiwan Mandarin), **any language**
  (translate to Taiwan Mandarin), or **English** (translate to Taiwan Mandarin).

## Step 2: Apply Taiwan Mandarin Patterns

Apply the rules below systematically. The goal: every 2-3 sentences should carry at
least one marker from particles, vocabulary, or spelling. Not every rule applies to
every sentence — pick the ones that fit naturally.

Taiwan Mandarin exists on a continuum. This skill targets the **light-to-heavy
colloquial range** — from a young Taiwanese texting a friend, up to 2000s BBS
netizen style. It deliberately **excludes caricature** (e.g., 鄉土劇 exaggeration).

---

### Grammar Patterns（語法模式）

#### G1. 「有」+ 動詞 — 完成/經驗體 [Hard, Light+]

Taiwanese Hokkien uses 有 + verb to mark completion or experience. This transfers into
Taiwan Mandarin, replacing the standard 了/過 in many casual contexts.

> **Standard:** 我吃過飯了。
>
> **Taiwan Mandarin:** 我有吃飯了。

> **Standard:** 你去過日本嗎？
>
> **Taiwan Mandarin:** 你有去過日本嗎？

> **Standard:** 他說過這件事。
>
> **Taiwan Mandarin:** 他有說過這件事。

#### G2. 「給我」句式 — 強化命令 / 經驗被動 [Hard, Medium+]

"給我" functions as either a command intensifier (sharp imperative) or a mild
experiential passive borrowed from Taiwanese 予我.

> **Command:** 給我過來！ / 給我閉嘴！ / 給我記住！
>
> **Experiential:** 他給我騙了一次。 (He tricked me — casual register)

#### G3. 「會」+ 形容詞 — 描述現在狀態 [Hard, Light+]

Taiwan Mandarin uses 會 + stative adjective to describe a **current** sensation
or state. This differs from Standard Mandarin where 會 + adjective would suggest
future possibility. The Hokkien-influenced usage treats pain, cold, itch, tiredness
etc. as states one "會"（ē, 台語「會」）rather than states one "is".

> **Standard (now):** 我疼。 / 這裡痛。
>
> **Taiwan Mandarin:** 我會痛。 / 這裡會痛。 *(not a future prediction — a present complaint)*

> **Standard (now):** 有點冷。
>
> **Taiwan Mandarin:** 會冷耶。

> **Standard (now):** 我很累。
>
> **Taiwan Mandarin:** 會累。

Note: the genuine future-possibility use of 會（「明天會下雨」）is NOT the target
pattern here; apply G3 only to present-state descriptions.

#### G4. 強化詞堆疊 [Hard, Light+]

Taiwan Mandarin has a rich inventory of intensifiers — stack them freely on adjectives
and verbs.

| 強化詞 | 用法 |
|---|---|
| 超 X | 超好吃、超累、超可愛 |
| 有夠 X | 有夠扯、有夠貴、有夠煩 |
| X 爆 / 爆了 | 帥爆、累爆了 |
| X 到爆 | 好吃到爆 |
| X 到不行 | 煩到不行、冷到不行 |
| X 到一個不行 | 誇張版 |
| 超級 X 的 | 超級好玩的 |

> **Standard:** 這家店很好吃。
>
> **Taiwan Mandarin:** 這家店超好吃的啦。

> **Standard:** 今天非常熱。
>
> **Taiwan Mandarin:** 今天熱到爆。

#### G5. 動詞重疊與「V 看看」[Soft, Light+]

Reduplicate verbs for tentativeness or liveliness; 「V 看看」adds "try and see."

> **Standard:** 試試。 / 嚐嚐。
>
> **Taiwan Mandarin:** 試試看。 / 吃吃看。 / 用用看。

> **Standard:** 走吧。
>
> **Taiwan Mandarin:** 走走走、走啦。

#### G6. 「是說」/「是怎樣」— 語用連接 [Soft, Medium+]

「是說」works like "by the way / speaking of"; 「是怎樣」expresses irritation or
rhetorical challenge.

> **Topic switch:** 是說你今天怎麼那麼早？
>
> **Irritation:** 你是怎樣啦？
>
> **Rhetorical:** 他是怎樣，幹嘛一直看我？

#### G7. 讓步句「X 是 X 啦，但是...」[Soft, Medium+]

Classic Taiwan yielding structure. Concede a point, then pivot.

> **Standard:** 雖然好看但太貴。
>
> **Taiwan Mandarin:** 好看是好看啦，但是太貴了。

> **Standard:** 他雖然是對的，但態度很差。
>
> **Taiwan Mandarin:** 他對是對啦，但態度有夠差。

#### G8. 主題句式強化 [Soft, Medium+]

Place the topic first, comment after — this pattern already exists in Mandarin but is
more pervasive and casual in Taiwan Mandarin, often with a sentence-final particle.

> **Standard:** 這件事很麻煩。
>
> **Taiwan Mandarin:** 這件事喔，有夠麻煩的啦。

> **Standard:** 那家店的咖啡很好喝。
>
> **Taiwan Mandarin:** 那家店的咖啡齁，超好喝的。

---

### Particle Patterns（語尾助詞）

Particles are the heartbeat of Taiwan Mandarin. They convey pragmatic meaning,
solidarity, and emotional texture. Use them abundantly but appropriately — each has
specific functions.

**Combination rule:** Usually one particle per sentence. The only common stacking is
「啦」after other particles for extra emphasis (「好啦」「是喔啦」rare).

#### P1. 啦 — 緩和 / 肯定 / 輕微不耐 [Hard, Light+]

The most iconic Taiwan Mandarin particle. Softens commands, signals reassurance,
expresses mild impatience, or builds intimacy.

> **Softening:** 好啦好啦，我知道了。
>
> **Reassurance:** 沒事啦，別擔心。
>
> **Impatience:** 走啦走啦，要遲到了。
>
> **Certainty:** 就是這樣啦。

#### P2. 喔 — 提醒 / 驚訝 / 輕柔警告 [Hard, Light+]

Marks friendly reminders, mild surprise, or a soft warning. Can carry a slightly
cute/warm tone.

> **Reminder:** 我要走了喔。
>
> **Surprise:** 是喔？真的假的？
>
> **Warning:** 要小心喔。
>
> **Soft confirmation:** 好喔。

#### P3. 耶 / 欸 — 驚喜 / 親暱 [Hard, Light+]

Expresses surprise, delight, or affectionate discovery. Often lightly exclamatory.

> **Delight:** 好厲害耶！
>
> **Discovery:** 真的耶！
>
> **Affection:** 你人真好欸。

**Position matters:** 欸 here is **sentence-final** (a particle). When 欸 appears
**sentence-initial** it's a different item — a vocative interjection ("hey!") covered
in S3. Same character, different pragmatic role; position disambiguates.

#### P4. 齁 / 吼 — 尋求同意 / 確認 [Hard, Medium+]

From Taiwanese 乎. Seeks agreement, confirms a shared observation, or softly challenges.

> **Agreement-seeking:** 這樣很好吃齁？
>
> **Confirming shared view:** 你也覺得他很機車齁。
>
> **Mock-challenging:** 你又遲到了吼！

#### P5. 啊 — 語氣開場 / 強化 [Hard, Light+]

Opens a turn with emphasis, or reinforces mid-sentence. Not to be confused with the
discourse-initial 啊 in 啊 ... 啊不就 frame.

> **Turn opener:** 啊你是怎樣？
>
> **Self-evident:** 啊不就這樣。 / 啊對啊。
>
> **Emphatic:** 好啊！ / 走啊！

#### P6. 捏 / ㄋㄟ — 撒嬌 / 親暱 [Soft, Medium+]

A cute, affectionate particle. Used to soften complaints or express playfulness.

> **Playful complaint:** 好冷捏。
>
> **Soft refusal:** 不要啦捏。
>
> **Affection:** 想你捏。

#### P7. 咧 / 勒 — 比較 / 疑問 [Soft, Light+]

Asks "what about X?" or trails off with rhetorical tone.

> **Comparison:** 你咧？ / 他咧？
>
> **Rhetorical:** 那要怎樣咧？
>
> **Soft probe:** 是嗎勒？

#### P8. 哦 / 噢 — 拉長接話 [Soft, Medium+]

Lengthens the response, often drawn out in text as 哦～ or 喔～. Conveys casualness
or lukewarm agreement.

> **Casual ack:** 是哦～
>
> **Lukewarm agreement:** 好哦。
>
> **Realisation:** 哦！原來是這樣。

---

### Vocabulary Patterns（詞彙模式）

#### V1. 台語借詞 — 核心集 [Hard, Light+]

Sprinkle these core Hokkien loanwords naturally. These are everyday Taiwan Mandarin
vocabulary, not exotica.

| 借詞 | 意思 | 備註 |
|---|---|---|
| 假掰 | 裝模作樣、矯情 | |
| 歹勢 | 不好意思、抱歉 | phái-sè |
| 阿沙力 | 乾脆、爽快 | < 日語 あっさり |
| 俗辣 | 膽小鬼 | sio̍k-lat |
| 凍未條 | 受不了 | tòng-bē-tiâu |
| 蝦米 / 蝦咪 | 什麼 | siánn-mih |
| 俗擱大碗 | 便宜又大碗 | |
| 蘇胡 | 舒服（音變） | |
| 鴨霸 | 蠻橫、霸道 | |
| 速配 | 相稱 | sio-phuè |
| 踹共 | 出來講 | tshu-âi-kóng（< tshut-lâi-kóng 省音） |
| 牽手 | 妻子 | |
| 夭壽 | 糟了、哎呀 | iáu-siū |

#### V2. 台語借詞 — 擴展集 [Hard, Medium+]

| 借詞 | 意思 |
|---|---|
| 靠北 | 哀嚎、抱怨、糟糕（粗） |
| 靠夭 | 同上，語氣更重 |
| 無三小路用 | 沒什麼用 |
| 喬事情 | 協調、安排 |
| 嗆聲 | 挑釁發言 |
| 機車 | 龜毛、難搞 |
| 白目 | 不識相 |
| 龜毛 | 吹毛求疵 |
| 走鐘 | 走樣、偏離 |
| 黑白來 | 亂來 |
| 抓狂 | 發狂、暴怒 |
| 衰小 | 倒楣 |
| 槓龜 | 沒中、失敗 |
| 聳 / 俗 | 土、不時尚 |
| 雞婆 | 愛管閒事 |

#### V3. 日語借詞 [Soft, Medium+]

| 借詞 | 意思 | 來源 |
|---|---|---|
| 多桑 | 父親 | とうさん |
| 歐巴桑 | 大媽、阿姨 | おばさん |
| 歐吉桑 | 大叔 | おじさん |
| 運將 | 司機 | 運ちゃん |
| 便當 | 飯盒 | 弁当 |
| 秀逗 | 故障、腦袋壞 | short |
| 麻吉 | 好朋友、很搭 | match |
| 甘巴爹 | 加油 | 頑張って |
| 斯剛以 | 厲害 | すごい |
| 阿里阿多 | 謝謝 | ありがとう |
| 歐嗨呦 | 早安 | おはよう |
| 莎喲娜拉 | 再見 | さようなら |

#### V4. 擬音字 — 音韻反映於書寫 [Hard, Medium+]

These are phonological features of Taiwan Mandarin written out. They emerged as
internet/BBS conventions and became iconic.

| 擬音字 | 標準字 | 音韻依據 |
|---|---|---|
| 偶 | 我 | 發音圓唇化 |
| 偶棉 / 偶們 | 我們 | 同上 |
| 粉 | 很 | ㄏ → ㄈ 鬆化 |
| 素 | 是 | ㄕ → ㄙ 去捲舌 |
| 速 | 是 | 變體 |
| 醬 | 這樣 | 合音 |
| 醬子 | 這樣子 | 合音 |
| 降 | 這樣 | 變體 |
| 釀 | 那樣 | 合音 |
| 蝦咪 / 蝦米 | 什麼 | 台語 siánn-mih |
| 企 | 去 | 音近（老派） |
| 窩 | 我 | 口語音近 |

**Usage guidance:**
- Light: no 擬音字
- Medium: use 粉、素、醬 / 醬子、蝦咪 sparingly (one or two per paragraph)
- Heavy: use liberally, including 偶、偶棉、降、釀

#### V5. 注音文 [Hard, Heavy]

BBS / 無名小站 / 奇摩即時通 era (ca. 2000–2010). Appears only in Heavy mode.

| 注音 / 混合 | 標準字 |
|---|---|
| ㄉ | 的 |
| ㄇ | 嗎 |
| ㄅ | 不 |
| ㄋ | 你 |
| ㄍ | 個 |
| ㄌ | 了 |
| 3Q | thank you |
| 881 | 掰掰了 |
| 520 | 我愛你 |
| ㄟ | 欸 |

> **Standard:** 我不知道是不是真的。
>
> **Heavy:** 偶ㄅ知ㄉ素ㄅ素真ㄉ。

#### V6. 網路次文化用語 [Soft, Medium+]

PTT / Dcard / FB 留言區常見。

| 用語 | 意思 | 出處 |
|---|---|---|
| 鄉民 | 網友 | PTT |
| 大大 | 高手、大佬 | PTT |
| 神人 | 厲害的人 | 網路 |
| 苦主 | 受害者 | PTT |
| 廠廠 | 呵呵（反諷） | PTT |
| XDD / XDDD | 大笑 | 通用 |
| QQ | 哭哭 | 通用 |
| 很狂 | 很猛 | 網路 |
| 超派 | 超酷、敢衝 | 網路 |
| GG | 完了、結束 | 遊戲 |
| 484 | 是不是（諧音） | 諧音 |
| 94 | 就是（諧音） | 諧音 |
| 吃土 | 月底沒錢 | 網路 |
| 跳針 | 重複不休 | 網路 |
| 淡定 | 冷靜、不動如山 | 網路（PTT） |

#### V7. 口語詞彙置換 [Hard, Light+]

Routinely swap standard written forms for casual Taiwan Mandarin equivalents.

| 標準 | 台灣國語 |
|---|---|
| 非常 | 超 / 有夠 / 超級 |
| 很好 | 超好 / 好棒棒 |
| 我的天啊 | 我的老天鵝啊 / 歐買尬 / 哎呀我的媽 |
| 真的 | 真的耶 / 真ㄉ / 真滴 |
| 什麼 | 蝦米 / 啥 / 三小（粗） |
| 怎麼辦 | 要怎辦 / 腫麼辦 |
| 不是 | ㄅ素（Heavy） / 不素 |
| 為什麼 | 為什麼啦 / 是為什麼 / 憑什麼 |
| 沒有 | 沒 / 母湯 / 母系（Heavy） |
| 可以 | 可 / OK 啦 |

**母湯** (bô-thang, 台語「不可以」) is a frequent Medium+ substitute for 不行/不可以.

---

### Structure Patterns（結構模式）

#### S1. 顏文字 / Emoticon [Hard, Medium+]

| 顏文字 | 意思 |
|---|---|
| ><  | 害羞、閉眼 |
| @@ | 暈、困惑 |
| QQ | 哭 |
| Orz / orz | 跪 / 無奈 |
| XD / XDD | 大笑 |
| :P | 吐舌 |
| (*´∀｀) | 可愛 |
| (￣▽￣)ﾉ | 打招呼 |

Place at sentence end to mark emotion — but only on sentences that carry a real
emotional peak. Overuse reads as performative, not authentic.

- Light: none
- Medium: at most one per paragraph, only at an emotional high point
- Heavy: at most 1-2 per paragraph; not every sentence needs one

#### S2. 語氣拉長 [Hard, Light+]

Elongate particles/words for casualness or coyness.

> 好喔～～
> 對啊啊啊
> 嗯嗯嗯
> 掰掰～

#### S3. 感嘆詞 [Hard, Light+]

| 感嘆詞 | 場合 |
|---|---|
| 哇 | 驚嘆 |
| 欸 | 招呼、引注 |
| 靠 | 驚呼（粗） |
| 靠北 | 哀嚎（粗） |
| 夭壽 | 糟了 |
| 哎呀 | 不悅 / 撒嬌 |
| 哎唷 | 撒嬌 / 小驚 |
| 天啊 / 我的天 | 驚嘆 |
| 我的老天鵝 | 誇張驚嘆 |
| 歐買尬 | Oh my god 音譯 |
| 媽呀 | 驚恐 |

#### S4. 標點擴增 [Soft, Medium+]

Extend punctuation for emotional color.

- ！！！ 多重驚嘆號 — 激動、強調
- ～～～ 波浪號 — 拉長、可愛
- ？？？ 多重問號 — 困惑、不敢置信
- ⋯⋯⋯⋯ 省略號加長 — 無言、欲言又止

---

## Step 3: Produce Taiwan Mandarin Output

Apply the checklist to transform the entire text. Aim for a natural, consistent
Taiwan Mandarin voice.

### Intensity Levels

Each rule is tagged with its minimum intensity (e.g., `[Hard, Light+]` = active from
Light up; `[Soft, Heavy]` = only in Heavy mode).

| Level | Active Rules | Effect |
|---|---|---|
| **Light** | G1, G3-G5, P1-P3, P5, P7, V1, V7, S2-S3. No 擬音字, no 注音文. | 一般台灣人日常 LINE 聊天，親切但不誇張。 |
| **Medium** (default) | Light + G2, G6-G8, P4, P6, P8, V2-V4, V6, S1, S4. 擬音字（粉/素/醬）偶用。 | 明顯台式口語，偶見擬音字與顏文字，像 PTT 八卦板輕鬆貼文。 |
| **Heavy** | All rules including V5（注音文）, 擬音字全開（偶/偶棉/降/釀）, 密集網路次文化用語。 | 2000 年代無名小站、奇摩即時通、BBS 鄉民風格，時代感強烈。 |

If the user doesn't specify, use **Medium**.

### Input-Specific Handling

**Mandarin input → Taiwan Mandarin:**
1. Identify formal / standard written phrases and swap them for casual Taiwan Mandarin
   counterparts (V7).
2. Add particles (P1-P8) to sentences that carry pragmatic meaning — softening,
   reassurance, agreement-seeking, surprise. Leave neutral/declarative sentences
   untouched. Rule of thumb: if you're asking how the speaker **feels** about what
   they're saying, a particle probably helps.
3. Replace vocabulary with loanwords where fitting (V1-V3).
4. Apply spelling transforms per intensity (V4, V5).
5. Add emoticons and structural markers per intensity (S1, S4) — only on emotional peaks.

**Non-Mandarin input (English, etc.) → Taiwan Mandarin:**
1. First translate into standard Mandarin, preserving meaning.
2. Then apply the Taiwan Mandarin transforms as above.

---

## Step 4: Output

1. **File output:** Save to `_taiwan` suffix (e.g., `article.md` → `article_taiwan.md`).
   If no file was provided, output directly in conversation.
2. **Show 3-5 representative sentence pairs** comparing Original and Taiwan Mandarin.
3. **List applied patterns:** Note which major pattern groups (G/P/V/S) were most
   active and why.
4. **Loanword glossary:** List any loanwords used (台語/日語) with brief meanings.

---

## Important Notes

- This is a **stylistic transformation tool** for creative, educational, and cultural
  purposes.
- Taiwan Mandarin is a **legitimate sociolect** with systematic grammar and lexicon,
  not random bad Mandarin. Treat it with linguistic respect.
- **Exclude caricature.** Do NOT produce 鄉土劇-style exaggeration, mocking imitation,
  or content that stereotypes Hokkien speakers as uneducated. The goal is authentic
  contemporary Taiwan Mandarin, not a joke dialect.
- **Particles are not random filler.** Each has specific pragmatic functions:
  - 啦 = solidarity/softening (not a catch-all)
  - 喔 = friendly reminder (not surprise)
  - 齁 = agreement-seeking (not certainty)
  - 耶 = delight/discovery
- **擬音字 are intensity-gated.** Light mode uses standard orthography; Medium uses
  basic 擬音字; Heavy goes all-in with 注音文.
- **Formal/classical input produces absurd output.** If the input is a legal contract,
  classical poetry, or government decree, warn the user before transforming — the
  result will be comical, not useful.
- When in doubt about a particle or spelling, think: "What would a Taiwanese friend
  type in a LINE chat?" That's the register we're aiming for.
