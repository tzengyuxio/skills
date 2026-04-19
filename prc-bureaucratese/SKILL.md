---
name: prc-bureaucratese
description: >
  Transform text into PRC party-state bureaucratese (中共公文體 / 黨政公文體) — the
  institutional writing style of Mainland China's Party and government documents,
  news bulletins, and official speeches. Features high-frequency action verbs
  (落實/加強/推進/深化), adverb-verb stacks (紮實推進/深入貫徹/全面落實),
  four-character parallel phrases (不忘初心、牢記使命), numerical political slogans
  (三個務必/四個全面/五位一體), New-Era ideological vocabulary (新時代/新發展格局/
  中國式現代化/偉大復興), and template openings/closings (以習近平新時代中國特色
  社會主義思想為指導... / 奮力譜寫新篇章). Three intensity levels from routine
  administrative notices up to full 黨八股 Party editorial style.
  Useful for creative writing, satire, historical simulation, translation
  comparison, or teaching rhetorical analysis.
  Triggers on "/prc-bureaucratese", "寫成公文體", "改成中共公文體", "黨政公文化",
  "黨八股化", "make it chinese official style", "PRC official style", "官樣文章".
argument-hint: [file-path]
allowed-tools: Read, Write, Edit, Glob
---

# PRC Bureaucratese — 中共黨政公文體

Transform text into PRC party-state bureaucratese (中共公文體, 黨政公文體) — the
distinctive institutional writing style of Mainland China's Party documents,
government reports, news bulletins, and leaders' speeches. The result should read
like a *People's Daily* editorial, a State Council notice, or a provincial Party
work report — abundant in formulaic phrases, parallel four-character couplets,
numerical slogans, and New-Era ideological vocabulary.

This is a **stylistic transformation tool**. It is not an endorsement of any
political program — the goal is to faithfully reproduce the recognizable rhetorical
texture of a real institutional register, in the same way this repo's other skills
reproduce Taiwan Mandarin, HK Chinese, or Classical Chinese without endorsing those
communities. Use it for creative writing, satire, historical simulation, rhetorical
analysis, or translation comparison.

## A word on 黨八股

Mao Zedong's 1942 essay《反對黨八股》identified eight "crimes" of party writing:
empty talk, posturing, obliviousness to audience, tedium, alphabet-list structure,
irresponsibility, poisoning the party, harming country and people. Ironically the
very features Mao denounced — formulaic phrases, empty abstraction, posturing
grandiosity — became **the** defining texture of PRC institutional writing in the
decades that followed. This skill reproduces that texture. Readers familiar with
Mao's essay will notice the self-parody; it is intentional.

## Arguments

- `$0` — (Optional) Path to a markdown or text file. If omitted, ask for inline text
  or find the most recent text in conversation context.

## Step 1: Load the Text

- If `$0` is provided, read the file.
- If no argument, find the most recent text in the conversation, or ask the user.
- The input can be **any Chinese text** (rewrite in bureaucratese), **any language**
  (translate to Mandarin then transform), or **English** (translate to Mandarin then
  transform).

## Step 2: Apply PRC Bureaucratese Patterns

Apply the rules below systematically. Goal: at Medium+, every clause should carry
at least one bureaucratese marker — an adverb-verb stack, a parallel four-character
phrase, a nominalized abstraction, or a template formula. Bureaucratese is
maximally **formulaic** — unlike most registers, repetition and predictability are
features, not bugs.

This skill targets **PRC 2010s-2020s New Era style** as the primary register,
while covering continuous traditions from earlier decades. Heavy mode leans fully
into contemporary Xi-era discourse (新時代, 中國式現代化, 新發展格局).

---

### Vocabulary Patterns（詞彙模式）

#### V1. 高頻動詞 — 行動與治理類 [Hard, Light+]

The core action vocabulary of bureaucratese. Swap ordinary verbs for these at every
intensity.

| 常用動詞 | 典型搭配 |
|---|---|
| **推進** | 推進改革、推進發展、推進建設 |
| **推動** | 推動高質量發展、推動轉型 |
| **落實** | 落實部署、落實要求、落實責任 |
| **貫徹** | 貫徹精神、貫徹決策 |
| **加強** | 加強領導、加強建設、加強監督 |
| **深化** | 深化改革、深化認識 |
| **統籌** | 統籌推進、統籌兼顧 |
| **完善** | 完善機制、完善制度 |
| **健全** | 健全體系、健全制度 |
| **優化** | 優化結構、優化布局 |
| **強化** | 強化責任、強化措施 |
| **構建** | 構建格局、構建體系 |
| **部署** | 作出部署、統一部署 |
| **抓好/抓實/抓細** | 抓好重點、抓實基礎、抓細措施 |

#### V2. 高頻副詞 — 紮實深入系列 [Hard, Light+]

These adverbs stack before verbs. Use liberally.

| 副詞 | 用法 |
|---|---|
| **紮實** | 紮實推進、紮實開展 |
| **深入** | 深入貫徹、深入推進、深入開展 |
| **切實** | 切實加強、切實做好 |
| **全面** | 全面落實、全面推進、全面深化 |
| **大力** | 大力推動、大力弘揚 |
| **著力** | 著力解決、著力培育 |
| **積極** | 積極推進、積極探索 |
| **穩步** | 穩步推進、穩步實施 |
| **持續** | 持續深化、持續優化 |
| **有序** | 有序推進、有序開展 |
| **堅定不移** | 堅定不移地推進 |
| **進一步** | 進一步深化、進一步增強 |

#### V3. 核心名詞概念 [Hard, Light+]

Swap everyday nouns for these abstract/institutional forms.

| 概念詞 | 常配對詞 |
|---|---|
| **發展** | 經濟發展、高質量發展、新發展理念 |
| **建設** | 黨的建設、生態文明建設 |
| **體系** | 治理體系、製度體系、監督體系 |
| **體制** | 體制機制、政治體制 |
| **機制** | 工作機制、協同機制 |
| **格局** | 新發展格局、工作格局 |
| **能力** | 治理能力、執政能力 |
| **水平** | 治理水平、服務水平 |
| **質量** / **品質** | 發展質量、工作質量 |
| **動能** | 新動能、發展動能 |
| **擔當** | 使命擔當、責任擔當 |
| **使命** | 初心使命、歷史使命 |

#### V4. 新時代政治詞彙 [Hard, Medium+]

The ideological-political lexicon of the Xi era. Use at Medium+ to signal
contemporary register.

| 詞彙 | 含義 / 用法 |
|---|---|
| 新時代 | 習時代的時間標籤 |
| 新發展理念 | 創新、協調、綠色、開放、共享 |
| 新發展格局 | 雙循環 |
| 高質量發展 | 經濟工作主題 |
| 共同富裕 | 分配性政策方向 |
| 中國式現代化 | 現代化路徑論述 |
| 偉大復興 | 民族復興敘事 |
| 中國夢 | 2012 以來核心口號 |
| 人民至上 | 黨政合法性敘事 |
| 全過程人民民主 | 民主論述對外表達 |
| 黨的全面領導 | 權力格局核心命題 |
| 以人民為中心 | 政策價值表述 |
| 守正創新 | 方法論 |
| 踔厲奮發、勇毅前行 | 精神狀態對偶 |

#### V5. 數字化政治套語 [Hard, Heavy]

Numbered political slogans — hallmarks of party discourse. At Heavy mode use liberally.

| 數字套語 | 內容（簡述） |
|---|---|
| **兩個確立** | 確立習核心地位、確立習思想指導地位 |
| **兩個維護** | 維護習核心、維護黨中央權威 |
| **三個代表** | 先進生產力、先進文化、最廣大人民 |
| **三個務必** | 不忘初心、謙虛謹慎、敢於鬥爭（二十大） |
| **四個意識** | 政治、大局、核心、看齊 |
| **四個自信** | 道路、理論、制度、文化 |
| **四個全面** | 小康、改革、法治、治黨 |
| **五位一體** | 經濟、政治、文化、社會、生態 |
| **六穩六保** | 穩就業、保民生等 |
| **八項規定** | 2012 起中央八項規定 |
| **十四個堅持** | 新時代方略十四條 |

Do **not** paraphrase these — reproduce the exact numerical form. 「四個全面」只能是「四個全面」，不能寫成「這四個全面性的工作」。

#### V6. 核心意識形態序列 [Hard, Heavy]

The full ideological canon, typically invoked in opening paragraphs at Heavy mode.

- 馬克思列寧主義
- 毛澤東思想
- 鄧小平理論
- 三個代表重要思想
- 科學發展觀
- **習近平新時代中國特色社會主義思想**（當代最重要）

---

### Structure Patterns（結構模式）

#### S1. 三件套排比 [Hard, Medium+]

Three parallel phrases — a signature rhetorical device. Can be subjects, verb
phrases, or objects.

> **動賓排比:** 站穩人民立場、把握人民願望、尊重人民創造、集中人民智慧
>
> **務必式排比:** 務必不忘初心、牢記使命；務必謙虛謹慎、艱苦奮鬥；務必敢於鬥爭、善於鬥爭
>
> **堅持排比:** 堅持黨的領導、堅持人民至上、堅持守正創新

Rule of thumb: Medium uses 3-4 parallel items; Heavy uses 4-7.

#### S2. 四字格對偶 [Hard, Medium+]

Four-character couplets, often two pairs joined.

| 四字格對偶 | 場合 |
|---|---|
| 堅定信心、同心同德 | 結尾號召 |
| 埋頭苦幹、奮勇前進 | 結尾號召 |
| 踔厲奮發、勇毅前行 | 精神狀態 |
| 空談誤國、實幹興邦 | 警示對偶 |
| 守正創新 | 方法論 |
| 自信自強、守正創新 | 雙對偶 |
| 自強不息、厚德載物 | 德性對偶 |

#### S3. 雙重目的 / 既要又要 [Soft, Medium+]

Parallel goal-pair structure. Signals comprehensive coverage.

> 既要 X，又要 Y。
>
> 一手抓 X，一手抓 Y。
>
> 不僅要 X，更要 Y。
>
> 以 X 促 Y，以 Y 保 X。

**Example:** 既要做大蛋糕，又要分好蛋糕。

#### S4. 動詞堆疊 — 抓好抓實抓細 [Hard, Medium+]

Stack 2-3 verbs with the same object.

> 抓好、抓實、抓細各項工作。
>
> 做好、做實、做細民生保障。
>
> 把握規律、把握趨勢、把握大勢。

#### S5. 名詞化升級 — XX性 [Hard, Medium+]

Convert adjectives/verbs to nouns via 「性」or「化」; signals abstract
institutional gravity.

| 普通說法 | 公文化升級 |
|---|---|
| 很重要 | 具有全局性、戰略性 |
| 大體上 | 具有根本性 |
| 變化快 | 具有歷史性 |
| 涉及面廣 | 具有系統性 |
| 核心的 | 根本性、決定性 |

#### S6. 修飾詞層層堆疊 [Soft, Heavy]

Pile up multiple adjectives / adverbs before a noun or verb. Classic 黨八股 feature.

> **Example:** 深入紮實有序穩步地推進改革
>
> **Example:** 全面、系統、深入、持續地推進
>
> **Example:** 切實、深入、紮實地抓好落實

Light 模式避免；Medium 偶用；Heavy 大量使用。

---

### Template Patterns（套話模板）

#### T1. 開頭套話 [Hard, Medium+]

Typical opening formulas.

| 套話 | 用法 |
|---|---|
| 以習近平新時代中國特色社會主義思想為指導 | Heavy 的標準開頭 |
| 深入貫徹 XX 精神 | 會議/文件開頭 |
| 根據 XX 部署 | 承接性開頭 |
| 按照 XX 要求 | 承接性開頭 |
| 圍繞 XX 主線 | 定位性開頭 |
| 聚焦 XX 目標 | 定位性開頭 |
| 堅持 XX 為重點 | 原則性開頭 |
| 以 XX 為根本遵循 | 原則性開頭 |

#### T2. 結尾套話 [Hard, Medium+]

Typical closing formulas. Heavy mode often has multi-layer parallel closings.

| 套話 | 用法 |
|---|---|
| 為 XX 作出新的更大貢獻 | 最常見結尾 |
| 奮力譜寫 XX 新篇章 | 宏大結尾 |
| 凝心聚力、奮勇前行 | 精神結尾 |
| 開創 XX 新局面 | 前瞻結尾 |
| 為實現中華民族偉大復興貢獻力量 | 政治正確結尾 |
| 以優異成績迎接 XX | 節點性結尾 |
| 譜寫 XX 嶄新篇章 | 遞進結尾 |

#### T3. 連接性套話 [Hard, Medium+]

| 套話 | 作用 |
|---|---|
| 進一步 X、進一步 Y | 遞進 |
| 不斷 X、不斷 Y | 持續 |
| 持續 X、持續 Y | 持續 |
| 要堅持 X、要堅持 Y | 強調 |

#### T4. 強調性套話 [Hard, Medium+]

| 套話 | 語氣強度 |
|---|---|
| 必須 X | 命令式 |
| 堅決 X | 強化 |
| 絕不 X | 排他性 |
| 毫不動搖 | 不變信念 |
| 始終 X | 一貫性 |
| 堅定 X | 堅定性 |

---

## Step 3: Produce PRC Bureaucratese Output

Apply the checklist to transform the text. Bureaucratese tolerates — even
encourages — redundancy and formulaic repetition; don't try to make it "tight" or
"clean". Lean into the stacked modifiers, parallel lists, and template closings.

### Intensity Levels

Each rule is tagged with its minimum intensity.

| Level | Active Rules | Effect |
|---|---|---|
| **Light** | V1-V3 (基本動詞/副詞/名詞), T3-T4 (連接/強調套話基本款). No political ideology, no numerical slogans, no opening/closing templates. | 地方政府日常工作通知、部門內部紀要。官樣但不誇張。|
| **Medium** (default) | Light + V4 (新時代詞彙), S1-S5 (排比/四字格/動詞堆疊/名詞化), T1-T2 (開頭結尾模板), 動詞+副詞頻繁搭配. | 部委會議紀要、省級工作報告、一般黨政公文。典型黨政公文風格。|
| **Heavy** | All rules including V5 (數字化套語全開), V6 (意識形態序列), S6 (修飾詞堆疊), 完整開頭結尾模板, 多層排比. | 黨報社論、政府工作報告、重要會議通稿、經典黨八股。極度形式化。|

If the user doesn't specify, use **Medium**.

### Input-Specific Handling

**Chinese input → Bureaucratese:**
1. Replace ordinary verbs with V1 action verbs; replace nouns with V3 abstract
   nouns.
2. Stack V2 adverbs before verbs.
3. Add S1 parallel triples or S4 verb stacks at major transition points.
4. At Medium+, insert V4 New-Era vocabulary where topically fitting; add S2
   four-character couplets.
5. At Heavy, open with T1 ideological framing and close with T2 patriotic formula;
   include V5 numerical slogans and V6 ideological canon where topically justified.

**Non-Chinese input → Bureaucratese:**
1. Translate to standard Mandarin first.
2. Apply the transformation pipeline above.

---

## Step 4: Output

1. **File output:** Save to `_bureaucratese` suffix (e.g., `article.md` →
   `article_bureaucratese.md`). If no file was provided, output directly in
   conversation.
2. **Show 3-5 representative sentence pairs** comparing Original and Bureaucratese.
3. **List applied patterns:** Note which major pattern groups (V/S/T) were most
   active.
4. **Glossary / canonical terms:** List any numerical slogans, ideological
   terms, or template formulas used, with brief paraphrase.

---

## Important Notes

- This is a **stylistic transformation tool** for creative writing, satire,
  simulation, and rhetorical analysis.
- PRC bureaucratese is a **real institutional register** — the everyday writing
  style of People's Daily, the State Council, and Party documents. The skill
  reproduces the style faithfully, which means the output **will sound exactly
  like 黨八股** at Heavy mode. That's the intended output.
- **Not a political statement.** Using the skill to transform a text into
  bureaucratese is no more a political endorsement than using `wenyan-xianqin`
  endorses Warring States philosophy. Treat the style as a cultural-linguistic
  object.
- **Numerical slogans are canonical — do not paraphrase.** 四個全面, 五位一體,
  兩個維護 have fixed forms. Reproduce them exactly or not at all.
- **Comic/absurd outputs are expected** when transforming trivial inputs
  (recipe, personal diary, children's story). This mismatch of register and
  content is one of the skill's most useful applications — for satire, for
  teaching rhetorical analysis, or for demonstrating the compositional
  hollowness of pure-form writing.
- **Distinct from `roc-bureaucratese-classic`** (1960s-80s ROC official style).
  That skill draws on Classical Chinese flavor (著即/仰即/爰/茲/台端/查照);
  this one draws on post-1942 Marxist-Leninist party language. They share the
  genus of "Chinese bureaucratese" but differ fundamentally in lexicon and era.
- **Echoes of 毛澤東《反對黨八股》are deliberate.** The ironic intertextuality —
  Mao's 1942 critique becoming the very style this skill reproduces — is part of
  the historical texture users should appreciate.
- When in doubt, think: "Would this appear in a *People's Daily* editorial or a
  government work report?" That's the register we target.
