---
name: roc-bureaucratese-classic
description: >
  Transform text into classical-era Republic of China bureaucratese (中華民國
  1960s-80s 公文體) — the distinctive semi-classical administrative writing style
  of the ROC government before the gradual 白話化 of the 1990s. Features
  single-character classical vocabulary (之/於/以/係/為/俾/爰), archaic connectives
  (茲/惟/嗣/俟/頃/殆/甫), hierarchical honorific terms (鈞/貴/本/職/台端/鈞長),
  fixed procedural formulas (查照/鑒核/核備/照辦/奉悉/敬悉/業經/迭經), and
  standard closing conventions (此致 XX 鈞鑒 / 為荷 / 特此函達). Three intensity
  levels from light administrative formality up to dense electrical-telegram-era
  concision.
  Useful for creative writing, historical simulation, satire, generation of
  period-appropriate bureaucratic text, or teaching rhetorical analysis.
  Triggers on "/roc-bureaucratese-classic", "寫成民國公文體", "改成中華民國公文",
  "舊式公文化", "民國公文化", "make it roc official style", "ROC classic
  bureaucratese", "仰即/著即 公文體".
argument-hint: [file-path]
allowed-tools: Read, Write, Edit, Glob
---

# ROC Bureaucratese (Classic Era) — 中華民國 1960s-80s 公文體

Transform text into classical-era Republic of China bureaucratese (中華民國公文體) —
the distinctive semi-classical administrative writing style that dominated ROC
government documents, court filings, corporate correspondence, and military
communiqués from roughly the 1960s through the 1980s, before the gradual 白話化
reform accelerated in the 1990s-2000s.

The result should read like a typical令/呈/咨/函 from a Taiwan government office
circa 1975: dense with 文言 single-characters (之/於/以/係), honorific hierarchy
(鈞/貴/本/職/台端), fixed procedural formulas (查照/鑒核/核備), and the
Republican-era ceremonial cadence inherited from late Qing official correspondence.

## Arguments

- `$0` — (Optional) Path to a markdown or text file. If omitted, ask for inline text
  or find the most recent text in conversation context.

## Step 1: Load the Text

- If `$0` is provided, read the file.
- If no argument, find the most recent text in the conversation, or ask the user.
- The input can be **any Chinese text** (rewrite in classical ROC bureaucratese),
  **any language** (translate to Mandarin then transform), or **English** (translate
  then transform).

## Step 2: Apply ROC Classic Bureaucratese Patterns

Apply the rules below systematically. Classical ROC bureaucratese is characterized
by:

- **文言濃度**: Single-character replacements (的→之, 是→係, 在→於, 用→以, 給→俾)
- **電報體式簡省**: Compressed constructions, dropped function words where context permits
- **敬語分層**: Hierarchical honorifics encoded at every reference (鈞/貴/本/職/台端)
- **套語系統**: Fixed procedural phrases have preferred forms — use them verbatim
- **段落結構**: Major documents follow 主旨—說明—辦法 format (post-1972) or
  similar traditional patterning

This skill targets the **period of peak 文言化** — 1960s through 1980s — when
ROC bureaucratese was still thick with classical vocabulary before the白話化
push. Post-1993 簡化公文 reforms are **not** the target; a separate skill
(未製作) would handle modern ROC style.

---

### Vocabulary Patterns（詞彙模式）

#### V1. 文言單字替換 [Hard, Light+]

Substitute classical single-characters for their modern-Chinese equivalents.
This is the most fundamental transformation and should apply at every intensity.

| 白話 | 文言 | 備註 |
|---|---|---|
| 的 | 之 | 所有格 |
| 是 | 係 | 判斷 |
| 在 | 於 | 介詞 |
| 用/拿 | 以 | 手段 |
| 因為 | 因 / 緣 | 因果 |
| 所以 | 故 / 是故 | 結果 |
| 給/讓 | 俾 | 使役 |
| 也 | 亦 | 副詞 |
| 又 | 復 / 又 | 連接 |
| 但是 | 惟 / 然 | 轉折 |
| 如果 | 如 / 倘 / 若 | 假設 |
| 不能 | 未能 / 難以 | 否定 |
| 必須 | 須 / 應 | 必然 |
| 認為 | 以為 / 認定 | 判斷 |
| 處理 | 辦理 / 處置 | 動作 |
| 知道 | 悉 / 知悉 | 認知 |

#### V2. 文言連接詞與語氣詞 [Hard, Light+]

Classical connectives that structure bureaucratic arguments. These are
functionally load-bearing; use them freely.

| 連接詞 | 白話 | 用法 |
|---|---|---|
| 茲 | 現在 / 此處 | 起敘、引介 |
| 爰 | 於是、因此 | 承接理由後的作法 |
| 惟 | 但是、然而 | 反面因素 |
| 蓋 | 大概、因為 | 道理分析 |
| 頃 | 不久前、剛剛 | 時間 |
| 迭 | 多次 | 頻率 |
| 嗣 | 往後、從此 | 後續 |
| 俟 | 等到 | 等待 |
| 旋 | 隨即 | 順承 |
| 甫 | 剛剛 | 新近 |
| 迄 | 到、至今 | 時段延續 |
| 殆 | 幾乎、恐怕 | 估量 |
| 咸 | 皆、都 | 全稱 |
| 遽 | 突然、立即 | 快速 |
| 亟 | 急切 | 緊迫 |
| 逕 | 直接 | 方式 |
| 滋 | 發生、生出 | 產生 |
| 抑 | 或、還是 | 選擇 |
| 至於 | 至於 | 轉題 |
| 復以 | 再以 | 補敘 |
| 茲經 | 現在已 | 完成 |
| 茲據 | 現在根據 | 引據 |

#### V3. 稱謂系統 [Hard, Light+]

Hierarchical honorifics — the signature marker of ROC classic bureaucratese.
Use consistently throughout a document.

**有隸屬關係（upper-lower in same hierarchy）:**
| 方向 | 對方稱 | 自稱 |
|---|---|---|
| 下→上 | 鈞（機關）/ 鈞長（首長）| 本 / 職 |
| 上→下 | 貴（機關）/ 該（第三方）| 本 |

**無隸屬關係（parallel or unrelated agencies）:**
| 方向 | 對方稱 | 自稱 |
|---|---|---|
| 下→上 | 大（機關）| 本 |
| 上→下 | 貴（機關）| 本 |

**對人民**: 台端 / 先生 / 女士 / 君 / 您 / 貴（團體）

**間接提及**: 該局 / 該員 / 該部 / 該管業務

**敬稱擴充**: 鈞鑒 / 大鑒 / 均鑒 / 台鑒（用於結尾「此致」之後）

#### V4. 引述語 [Hard, Medium+]

Citation formulas depending on the cited source's hierarchical position.

| 對上引述 | 對平行/下級引述 |
|---|---|
| 奉 | 依據 |
| 奉交下 | 依照 |
| 奉示 | 根據 |
| 業經奉准 | 經查 |
| 諒蒙鈞察 | 諒達 / 計達 |

**復文語**:
- 奉悉（回復上級來文時用）
- 敬悉（回復平行機關來文時用）
- 已悉（回復下級機關來文時用）
- 復（稱謂）……函（引復文件）

#### V5. 經辦語 — 案件處理狀態 [Hard, Medium+]

Fixed phrases for describing case handling. Use before V1 verbs.

| 經辦語 | 意思 | 用法 |
|---|---|---|
| 遵經 / 遵即 / 旋即 | 遵循辦理 | 對上級表達已辦 |
| 業經 / 已經 / 爰經 / 嗣經 | 已經辦理 | 通用 |
| 甫經 / 頃經 | 不久前辦理 | 強調新近 |
| 均經 / 並經 | 都已辦理 | 多件均辦 |
| 迭經 / 歷經 / 續經 | 多次辦理 | 強調頻次 |
| 當經 / 前經 / 復經 / 旋經 | 當時曾辦 | 歷史事件 |
| 俟經 | 等到辦理之後 | 前置條件 |

#### V6. 准駁語 [Hard, Medium+]

Approval/denial formulas, graded by hierarchy and stance.

**對下級准許**: 應予照准、准予照辦、准予備查、准予所請、如擬辦理

**對下級駁回**: 未便照准、礙難照准、應毋庸議、應予緩議、應予不准、應予駁回、所請不准

**對平行同意**: 敬表同意、同意照辦

**對平行拒絕**: 歉難同意、礙難同意、無法照辦、未便照辦

**對人民同意/拒絕**: 敬表同意 / 礙難同意 / 歉難同意

**長官批核**: 如擬、依議、可、照准、准如所請、應從緩議

#### V7. 期望語 [Hard, Medium+]

Request formulas — the verb-object core of many ROC documents.

**對上**: 請鑒核 / 請核示 / 請釋示 / 請核備 / 請鑒察 / 請核轉

**對平行**: 請查照 / 請察照 / 請卓參 / 請查照見復 / 請查明見復 / 請查照辦理見復 / 請查照備案 / 請查照轉知

**對下**: 請查照 / 希查照 / 請查照見復 / 請轉行照辦 / 請剋日見復

**內部/簽文**: 請核示 / 請鈞閱 / 請核閱 / 請鑒察 / 請鑒核 / 請鈞參

#### V8. 文言形容詞與副詞 [Soft, Medium+]

Classical modifiers that carry bureaucratic gravity.

| 詞 | 意思 | 例 |
|---|---|---|
| 殊堪 | 非常值得 | 殊堪嘉許 |
| 甚鉅 | 非常重大 | 影響甚鉅 |
| 至為 | 極為 | 至為重要 |
| 諒必 | 想必 | 諒必鑒察 |
| 未臻 | 尚未達到 | 未臻完備 |
| 尚難 | 仍難以 | 尚難認定 |
| 殊無 | 實無 | 殊無可議 |
| 莫此為甚 | 沒有比這更嚴重 | 違法莫此為甚 |
| 昭然若揭 | 真相大白 | 案情昭然若揭 |

#### V9. 特有成語與套詞 [Soft, Medium+]

| 套詞 | 用法 |
|---|---|
| 合先敘明 | 先行說明背景後 |
| 未敢擅專 | 不敢擅自決定 |
| 應毋庸議 | 不必再討論 |
| 併予澄明 | 同時澄清 |
| 綜上所述 | 總結 |
| 究其原因 | 分析原因 |
| 本於權責 / 本於職權 | 本於該有的責任 |
| 自行核處 | 自行決定處理 |
| 俾憑辦理 | 作為辦理依據 |
| 為資周妥 | 為求周詳 |
| 諒蒙鈞察 | 上級大概已知悉 |
| 旨揭 / 前揭 / 上揭 | 主旨 / 前面 / 上面所提 |
| 邇來 | 最近、近來 |
| 盱衡 | 檢視情況 |
| 卓見 / 惠賜卓見 | 高見 |
| 殊堪嘉許 | 非常值得嘉獎 |

---

### Structure Patterns（結構模式）

#### S1. 主旨—說明—辦法 三段格式 [Hard, Medium+]

Post-1972 standard function document (函) format. Use at Medium+ when producing
a document-length output.

```
主旨：（用「請」、「希」等期望語開頭，一段一句概括目的）

說明：（分點說明背景、事實、依據）
一、……
二、……

辦法：（提出具體辦理方式）
一、……
二、……
```

**Example 主旨 片段:**
- 主旨：為辦理 XX 事宜，請查照。
- 主旨：檢送 XX，請鑒核。
- 主旨：函轉 XX，請查照辦理。

#### S2. 電報體式省字 [Soft, Heavy]

Compressed forms dropping function words and pronouns where context permits.
Heavy mode 特徵 — pre-1972 特別明顯，reflecting the telegraph tradition of
bureaucratic correspondence.

> **白話：** 我已經收到你的信件，並且已經審閱過了。
>
> **公文：** 大函敬悉，已逕予審閱。

> **白話：** 為了辦理這件事情，希望請貴單位協助。
>
> **公文：** 為辦理本案，請貴單位鼎力惠助。

#### S3. 文言疑問/反詰句 [Soft, Heavy]

Classical rhetorical questions for emphasis.

- 安能置法令於不顧？（豈可）
- 豈可任其擾攘？（怎可）
- 何以為繼？（如何）
- 寧有他哉？（難道還有嗎）

#### S4. 四字格公文習語 [Hard, Medium+]

Stock four-character phrases that populate ROC bureaucratese.

| 四字格 | 意思 / 用法 |
|---|---|
| 刻不容緩 | 不能拖延 |
| 窒礙難行 | 實行有困難 |
| 礙難照辦 | 無法遵照辦理 |
| 毋庸贅述 | 不必多說 |
| 應毋庸議 | 不必討論 |
| 不容置疑 | 確定無疑 |
| 未敢擅專 | 不敢擅斷 |
| 併予澄明 | 一併說明 |
| 昭然若揭 | 真相大白 |
| 莫衷一是 | 無法決斷 |
| 邇來頻仍 | 近來經常 |
| 寬列預算 | 多編預算 |
| 酌情處理 | 按情況處理 |
| 依法處斷 | 依法處理 |
| 實為必要 | 確實需要 |
| 殊堪嘉許 | 值得嘉獎 |

---

### Template Patterns（套話模板）

#### T1. 開頭套話 [Hard, Medium+]

| 套話 | 用法 |
|---|---|
| 查……（引入案由事實） | 通用起首 |
| 茲為……（引入目的） | 通用 |
| 有關……一案 | 具體案由 |
| 關於……一事 | 具體事項 |
| 為辦理……事宜 | 目的開頭 |
| 茲據……報稱 | 引據報告 |
| 奉鈞部……函 | 引據上級 |
| 依據……規定 | 依法行政 |

#### T2. 結尾套話 [Hard, Medium+]

Classic closing formulas. Different document types have preferred endings.

| 套話 | 文類 / 用法 |
|---|---|
| 此致 | 函件結尾（後接鈞鑒/台鑒等） |
| 此上 | 函件結尾 |
| 此布 | 告示結尾 |
| 特此函達 | 函告結尾 |
| 特此通知 | 通知結尾 |
| 為荷 | 請求類結尾（平行） |
| 為禱 | 請求類結尾（祈望） |
| 為盼 | 請求類結尾（盼望） |
| 為幸 | 請求類結尾（慶幸） |
| 為要 | 命令/請求類（重要） |
| 是所至盼 | 最後祈望 |
| 謹陳鈞鑒 | 呈文結尾（對上） |
| 敬陳鈞核 | 呈文結尾（對上） |

**完整結尾範例**:
- ……請查照為荷。
- ……希查照辦理為要。
- 此致 XX 部 鈞鑒（下對上）
- 此致 XX 府 大鑒（無隸屬）
- 此致 XX 局 台鑒（平行）

#### T3. 特定文類套語 [Soft, Heavy]

Document-type-specific conventions.

- **令文**: 開頭「查」，具體敘明事由；結尾「此令」或「為要」
- **呈文**: 開頭「謹呈」或「竊查」；結尾「謹陳鈞鑒」
- **咨文**: 平行機關間正式對話，文言濃度較高
- **函**: 最常見的現代公文類型，有主旨-說明-辦法格式
- **公告**: 開頭「茲」；結尾「此布」
- **通報**: 開頭「茲將 XX 通報如次」；結尾「希查照」

#### T4. 敬語修飾 [Soft, Medium+]

Small deferential additions that raise the overall formality.

- 諒蒙鈞察（上級大概已知悉）
- 諒達 / 計達（平行/下級應已收到）
- 敬希 鑒核（恭敬請求審核）
- 敬請 核示
- 敬祈 惠予
- 敬祈 賜知
- 並祈 卓參

---

## Step 3: Produce ROC Classic Bureaucratese Output

Apply the transformation systematically. Classical ROC bureaucratese is
**ceremonial** — every reference to parties encoded in honorifics, every verb
of disposition wrapped in fixed formulas. Leaning into the文言濃度 and honorific
density is the skill.

### Intensity Levels

Each rule is tagged with its minimum intensity.

| Level | Active Rules | Effect |
|---|---|---|
| **Light** | V1 (基本單字替換), V2 (常見連接詞), V3 (稱謂系統), V6-V7 (基本准駁/期望語基本款), T1-T2 (開頭結尾模板基本款). | 標準機關公函行文，略帶文言味但可讀性高，類似 1980s 後期向白話化過渡的風格。|
| **Medium** (default) | Light + V2 全開 (惟/爰/嗣/俟), V4 (引述語), V5 (經辦語), V8 (文言形容詞副詞), V9 (套詞), S1 (主旨-說明-辦法), S4 (四字格), T3-T4. | 典型 1970s-80s 中期 ROC 公文，文言密度高但仍可辨識。|
| **Heavy** | All rules including S2 (電報體式省字), S3 (文言疑問/反詰句), V3 擴充敬語全用, 全段去白話化. | 1960s 至 1970s 初期的重度文言公文，近乎電報體，非常密集的文言單字與敬語系統。|

If the user doesn't specify, use **Medium**.

### Input-Specific Handling

**Chinese input → ROC classic bureaucratese:**
1. Replace V1 白話 single-characters with 文言 equivalents systematically.
2. Identify parties and apply V3 honorifics (鈞/貴/本/職/台端) consistently.
3. Replace ordinary verbs with V6-V7 bureaucratic formulas where context fits
   (decisions, requests, acknowledgements).
4. At Medium+, add V2 連接詞 (惟/爰/茲/嗣), V4-V5 citation and case-handling
   formulas, V8-V9 classical modifiers.
5. At Medium+, restructure document-length outputs into 主旨-說明-辦法 format
   (S1) if appropriate.
6. Apply T1 opening and T2 closing templates.
7. At Heavy, compress using S2 telegraph-style abbreviations.

**Non-Chinese input → ROC classic bureaucratese:**
1. Translate to standard written Mandarin first.
2. Apply transformation pipeline above.

---

## Step 4: Output

1. **File output:** Save to `_roc_classic` suffix (e.g., `article.md` →
   `article_roc_classic.md`). If no file was provided, output directly in
   conversation.
2. **Show 3-5 representative sentence pairs** comparing Original and the ROC
   bureaucratese version.
3. **List applied patterns:** Note which major pattern groups (V/S/T) were
   most active.
4. **Glossary:** Briefly explain any dense文言 vocabulary, honorific terms,
   or template formulas used.

---

## Important Notes

- This is a **stylistic transformation tool** for creative writing, historical
  simulation, satire, or teaching rhetorical analysis.
- Classic ROC bureaucratese is a **real historical register** — the everyday
  writing of government, courts, and corporations in Taiwan roughly 1960s-80s,
  before the白話化 push of the 1990s-2000s.
- **Distinct from `prc-bureaucratese`.** That skill draws on post-1942
  Marxist-Leninist Party language (黨八股, 落實/加強/推進/三個務必/五位一體).
  This skill draws on pre-白話化 classical semi-literary administrative style
  inherited from Republican and late Qing traditions. They share the genus of
  "Chinese bureaucratese" but differ fundamentally:
  - **PRC** — 白話 + 政治意識形態語彙 + 排比口號 + 數字化套語
  - **ROC classic** — 文言 + 敬語層級 + 單字省略 + 程序套語
- **Honorifics are hierarchically strict.** 鈞 is reserved for superior
  bodies; 貴 for peers or inferiors; 本/職 for self-reference. Mismatching
  honorifics is an obvious tell of unfamiliarity with the register — be
  consistent.
- **Fixed formulas are canonical.** 查照, 鑒核, 核備, 照辦, 奉悉, 敬悉, 已悉
  have fixed distributional patterns (which hierarchical direction each
  applies to). Respect them.
- **Comic/absurd outputs are expected** when transforming trivial inputs
  (diary, recipe, children's story). That mismatch is one of the skill's
  most useful applications — for satire or teaching.
- **Target period is 1960s-80s**, not modern ROC documents (which have been
  gradually 白話化 since 1993's《公文格式改革》). If the user wants a
  modern-style clean Taiwan official document, this skill produces something
  deliberately outdated.
- When in doubt, think: "Would this appear in a 1975 Taipei 市政府 函, a
  military high command 令, or a state enterprise 呈文?" That's the register
  we target.
