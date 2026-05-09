# Skills — Chinese Register & Style Transformation Toolkit

A systematic skill collection targeting the **registers, styles, regional varieties, historical layers, and literary genres of Chinese text**, built for [Claude Code](https://docs.anthropic.com/en/docs/claude-code) and compatible AI coding agents.

Currently 43 skills across 10 categories:

| Category | Count | Skills |
|---|---|---|
| AI writing style | 1 | humanize (remove AI tics) |
| Translation accent | 2 | dewesternise / westernise |
| Chinese-English hybrid | 4 | chinglish / singlish / hanjify / jingjing-style |
| Regional Chinese | 9 | taiwan / hongkong / singapore / mainland / dongbei / shanghainese / sichuan / written-hokkien / written-cantonese |
| Applied writing | 2 | prc-bureaucratese / roc-bureaucratese-classic |
| Classical Chinese | 4 | wenyan-xianqin / hanwei / guwen / huaben |
| Literary genre | 12 | koanify / liaozhai-tale / qiongyao-style / gulong-style / jinyong-style / shakespeare-style / eileen-chang-style / yu-guangzhong-style / bagu-essay / hemingway-style / lu-xun-style / sherlock-holmes-style |
| Classical Poetry | 2 | tang-poem-style / song-ci-style |
| Interpretive lens | 2 | psychoanalytic-lens / postmodern-lens |
| Internet vernacular | 4 | feihua-literature / zhiyin-style / versailles-literature / concrete-42 |

> [中文版](./README.md)

## Highlights

- **Controllable intensity spectrum**: translation-accent and regional-variety skills offer **Light / Medium / Heavy** levels (other categories produce a single targeted output, no intensity tiers)
- **Systematic checklists**: each skill has 20-30 explicit rules, every one tagged with firmness and (where applicable) minimum intensity — reproducible and traceable
- **Linguistic rigor**: each skill demarcates its linguistic scope, cites relevant research (邵敬敏, Jerry Norman, 胡適, etc.), grounds rules in real corpora, and **rejects caricature** — language varieties are treated as legitimate systems, not targets of mockery
- **Inverse pairs and composability**: two duality pairs — `dewesternise` ↔ `westernise`, and `gulong-style` ↔ `jinyong-style` (terse-with-aphorism vs chapter-form-with-named-moves); skills can be chained (e.g. `dewesternise` → `taiwan-mandarin`)
- **Public demos separated from local tests**: each skill's [`examples/`](./examples/) folder holds clean showcases; the shared [`examples/source-texts/`](./examples/source-texts/) corpus lets you compare skills side-by-side

## Available Skills

### AI Writing Style

| Skill | Function |
|-------|----------|
| [humanize](./humanize/) | Remove AI-generated writing patterns (26-item checklist, supports English & Chinese) |

### Translation Accent Tools

Style transformation tools for Europeanized Chinese (翻譯腔), each with a 25-item checklist. These two skills are inverse operations.

| Skill | Function |
|-------|----------|
| [dewesternise](./dewesternise/) | Remove Europeanized writing patterns from Chinese text |
| [westernise](./westernise/) | Deliberately add translation accent (3 intensity levels) |

### Chinese-English Language Mashup

English varieties and writing system transformations — convert text into Chinese-influenced English styles or hybrid scripts.

| Skill | Function |
|-------|----------|
| [chinglish](./chinglish/) | Transform Chinese or English into Chinglish — systematic L1-transfer patterns from Chinese grammar |
| [singlish](./singlish/) | Transform any text into Singlish — Singaporean English creole blending Hokkien, Malay, Cantonese, and Tamil |
| [hanjify](./hanjify/) | Transform English into Hanjified English — Hanzi carries meaning, English grammar stays intact (okurigana-style morphology) |
| [jingjing-style](./jingjing-style/) | Transform text into Jingjing-style — Chinese base sprinkled with unnecessary simple English words (amazing/busy/hot/fashion); the show-off vibe comes from "could've used Chinese, chose English"; a Taiwanese media-celebrity vernacular emerging in 2016; Light/Medium/Heavy intensity tiers |

### Regional Chinese Varieties

Transform text into regional sociolects / written registers of contemporary Chinese-speaking communities, each with a checklist and three intensity levels.

| Skill | Function | Example |
|-------|----------|---------|
| [taiwan-mandarin](./taiwan-mandarin/) | Transform text into Taiwan Mandarin — Hokkien/Japanese loanwords, phonological respellings (偶/粉/素/降), BBS-era 注音文, and sentence-final particles (啦/喔/齁/耶) | [demo](./taiwan-mandarin/examples/demo.md) |
| [hongkong-chinese](./hongkong-chinese/) | Transform text into Hong Kong Chinese — HK-specific terms (巴士/的士/雪櫃), transliterations (荷里活/梳化/三文治), English code-mixing, AB/BA word-order flips; Heavy mode extends to full written Cantonese (係/唔/嘅/咗/佢/呢/嗰) | [demo](./hongkong-chinese/examples/demo.md) |
| [singapore-mandarin](./singapore-mandarin/) | Transform text into Singapore Mandarin (Huayu) — SG administrative vocabulary (組屋/德士/樂齡/客工), Hokkien borrowings (幾時/不懂/做工/怕輸), Malay loanwords (甘榜/巴剎/atas/bodoh), post-verbal 先 placement, 千-based number units; the Mandarin counterpart to singlish | [demo](./singapore-mandarin/examples/demo.md) |
| [dongbei-mandarin](./dongbei-mandarin/) | Transform text into Northeastern Mandarin (東北話) — three-province speech rhythm (Heilongjiang/Jilin/Liaoning) with marker words 賊/嘎哈/咋整/老鐵/妥妥的; rooted in Zhao Benshen sketches, Errenzhuan, Douyin laotie streamers; Light/Medium/Heavy intensity tiers | [demo](./dongbei-mandarin/examples/demo.md) |
| [shanghainese](./shanghainese/) | Transform text into Shanghainese / Wu Chinese — pronoun swap (儂/阿拉/伊), negation (弗/勿/覅), sentence-final particles (呃/嘞/伐), Haipai vocabulary (結棍/霞氣/嗲/戇/淘漿糊); Jin Yucheng's《繁花》-style register; Light/Medium/Heavy intensity tiers | [demo](./shanghainese/examples/demo.md) |
| [sichuan-mandarin](./sichuan-mandarin/) | Transform text into Sichuan / Chongqing Mandarin — Southwestern Mandarin Chengyu cluster, jianghu attitude + heavy 兒化 + dense sentence-final particles (嘛/噻/嘞/哈); marker words 巴適/安逸/莫得/搞快點/龜兒; channels《Let the Bullets Fly》《Chongqing Hot Pot》; Light/Medium/Heavy intensity tiers | [demo](./sichuan-mandarin/examples/demo.md) |
| [written-hokkien](./written-hokkien/) | Transform text into written Taiwanese Hokkien — syntax follows Hokkien (not Chinese translation), uses native characters (阮/咱/怹/ê/beh/攏/毋/莫); two intensity tiers: Light (pure Hanzi, MOE-recommended 700 chars) / Heavy (Han-Romaji mix with Tâi-lô); rooted in Lai Ho / Cheng Ching-wen / Asia Babuja literary tradition | [demo](./written-hokkien/examples/demo.md) |
| [mainland-mandarin](./mainland-mandarin/) | Transform text into PRC mainland Mandarin (everyday / media register) — mainland-specific vocabulary (視頻/質量/出租車/公交/軟件) + internet slang (內卷/躺平/yyds/破防/絕絕子/家人們) + Weibo/Douyin/Bilibili/Xiaohongshu register; explicitly distinct from prc-bureaucratese (party-state register); Light/Medium/Heavy intensity tiers | [demo](./mainland-mandarin/examples/demo.md) |
| [written-cantonese](./written-cantonese/) | Transform text into full written Cantonese (syntax also Cantonese-ized) — core function words (係/唔/嘅/咗/佢/喺) + sentence-final particles (喎/啦/㗎/咩) + Cantonese word order (postposed adverbs / postposed verb-complements / direct-before-indirect double objects); rooted in TVB / Apple Daily / LIHKG; Light/Medium/Heavy intensity tiers | [demo](./written-cantonese/examples/demo.md) |

### Applied Writing Registers (應用文類)

Institutional/register-specific transformation tools for Chinese applied-writing genres. Currently two bureaucratese skills; the category leaves room for future additions (letters, notices, contracts, meeting minutes, autobiographies, etc.).

| Skill | Function | Example |
|-------|----------|---------|
| [prc-bureaucratese](./prc-bureaucratese/) | Transform text into PRC party-state bureaucratese — action verbs (落實/加強/推進/深化), adverb-verb stacks (紮實推進/深入貫徹/全面落實), four-character couplets (不忘初心、牢記使命), numerical political slogans (四個全面/五位一體), New-Era ideological vocabulary | [demo](./prc-bureaucratese/examples/demo.md) |
| [roc-bureaucratese-classic](./roc-bureaucratese-classic/) | Transform text into 1960s-80s ROC bureaucratese — classical single-char vocabulary (之/於/以/係/為/俾/爰), archaic connectives (茲/惟/嗣/俟/頃), hierarchical honorifics (鈞/貴/本/職/台端), procedural formulas (查照/鑒核/核備/奉悉), and the 主旨-說明-辦法 document format | [demo](./roc-bureaucratese-classic/examples/demo.md) |

### Classical Chinese Rewriting

Rewrite modern Chinese into different historical literary styles, each with a 20-22 item checklist.

| Skill | Style | Representative Works |
|-------|-------|---------------------|
| [wenyan-xianqin](./wenyan-xianqin/) | Pre-Qin Philosophical (先秦諸子體) | Analects, Zhuangzi, Han Feizi |
| [wenyan-hanwei](./wenyan-hanwei/) | Han-Wei Historical Narrative (漢魏史傳體) | Shiji, Hanshu, Records of the Three Kingdoms |
| [wenyan-guwen](./wenyan-guwen/) | Tang-Song Classical Essay (唐宋古文體) | Han Yu, Su Shi, Ouyang Xiu |
| [wenyan-huaben](./wenyan-huaben/) | Vernacular Fiction (話本小說體) | Water Margin, Romance of the Three Kingdoms, Dream of the Red Chamber |

### Literary Genre Rewriting

Rewrite text into specific literary genres — not just stylistic tweaks, but reorganizing narrative structure, character roles, and rhetorical economy. Room is left for future genres (fables, fairy tales, mythology, mystery, fantasy, etc.).

| Skill | Function |
|-------|----------|
| [koanify](./koanify/) | Rewrite into a narrative-style Zen koan — Hakuin's "Is that so?" tradition, 100–400 chars, white-vernacular with light classical particles, one of eight closure techniques |
| [liaozhai-tale](./liaozhai-tale/) | Rewrite into a 聊齋 classical short tale — Pu Songling tradition, 200–800 chars in pure 文言, one element transposed into the supernatural register (fox spirit / ghost / etc.) |
| [qiongyao-style](./qiongyao-style/) | Rewrite into Mid-Era Qiongyao romance — 《在水一方》《一簾幽夢》 tradition, 300–800 chars literary modern vernacular, mandatory love axis with structural obstacle, ache-preserving ending |
| [gulong-style](./gulong-style/) | Rewrite into Mid-late Gulong wuxia — post-1969《多情劍客無情劍》 mature period, 200–600 chars with extreme short-sentence rhythm, embedded aphorisms, mandatory contrast tension, no battle process |
| [jinyong-style](./jinyong-style/) | Rewrite into Mid-Era Jinyong wuxia — 1957–1969 five major works (Condor / Return / Heaven Sword / Demi-Gods / Smiling), 400–1200 chars chapter-form long sentences, named moves + classical poetry inlay + historical anchoring |
| [shakespeare-style](./shakespeare-style/) | Rewrite into Zhu-Shenghao-style Chinese translation of Shakespearean tragedy — four great tragedies (Hamlet/Lear/Othello/Macbeth), 300–1000 chars half-classical-half-vernacular dramatic register, dense metaphors + expressive rhythm + monologues (≥30%) |
| [eileen-chang-style](./eileen-chang-style/) | Rewrite into Eileen Chang style — mandatory desolate undertow, signature image cluster (moon / mirror / silk / old-Shanghai apartments), female gaze + detail-as-violence + anti-climactic ending; emotion held under, never burst |
| [yu-guangzhong-style](./yu-guangzhong-style/) | Rewrite into Yu Guangzhong essay style — mandatory classical-vernacular interlock, long-sentence cascade + true parallelism + classical-poem incorporation, geographical anchors restricted to Yu's actual biographical footprints (Chongqing / Xiamen / Shatin / Sizihwan) |
| [bagu-essay](./bagu-essay/) | Rewrite into Ming-Qing eight-legged essay — mandatory eight sections (破題/承題/起講/入手/起股/中股/後股/束股), four "stocks" in strict couplets, "speak in the voice of the sage" forbids first person, includes Wang Ao's《百姓足君孰與不足》as reference sample |
| [hemingway-style](./hemingway-style/) | Rewrite into Hemingway-style Chinese translation — iceberg theory (seven-eighths under water), short sentences + verb-driven + concrete nouns, repetition anchoring (same word / structure / action), Europeanized translation flavor is a feature, not a violation |
| [lu-xun-style](./lu-xun-style/) | Rewrite into Lu Xun voice — chilly-ironic early-vernacular Chinese: Wenyan-Baihua mixing + signature particles (然而/便/罷了/未免/實在/想來) + first-person 「我」 + ironic distance (neither mocking nor endorsing); positioned as stylistic homage rather than political mimicry, with irony targets restricted to abstract universals (national character / bystanders / petty self-preservation) |
| [sherlock-holmes-style](./sherlock-holmes-style/) | Rewrite into Zhu-Shenghao-style Chinese translation of Victorian detective fiction (Conan Doyle's Sherlock Holmes canon) — first-person Watson recollection + Holmes deductive monologue ("My dear Watson") + three-act case structure (client arrives → scene investigation → deductive reveal) + Victorian object density (gas lamp / pocket watch / pipe / hansom cab / Mrs. Hudson / Scotland Yard); world-building must use Western proper nouns (no Chinese-setting transposition); Chinese translation accent is a feature; Light/Medium/Heavy intensity tiers |

### Classical Poetry

Compress, distill, and refine prose into Chinese classical regulated verse. Locks in hard prosody (tonal patterns, rhyme groups, parallelism); imagery is carried by classical-image transposition. Room is left for future verse forms (yuefu, gexing, Yuan qu, additional ci tunes, etc.).

| Skill | Function |
|-------|----------|
| [tang-poem-style](./tang-poem-style/) | Rewrite into a Tang-style regulated poem — pick one of four canonical formats (五絕 5-char quatrain / 七絕 7-char quatrain / 五律 5-char regulated / 七律 7-char regulated); single-rhyme-group throughout per 平水韻 + tonal patterns 平仄譜 (both 平起 and 仄起 variants documented) + mandatory parallelism in middle two couplets (頷聯/頸聯) for 律詩, three-layer matching (part-of-speech / structure / tone); classical-image transposition (modern object → Tang equivalent: tram → carriage / key → jade lock); 起承轉合 four-part progression + closing line forbids didactic preaching; six Tang-poem reference samples (Wang Wei / Li Bai / Du Mu / Li Shangyin / Du Fu × 2) |
| [song-ci-style](./song-ci-style/) | Rewrite into a Song-dynasty 詞 (ci) — pick one of five canonical 詞牌 (tune-titles): 水調歌頭 (95 chars, long-medium) / 念奴嬌 (100 chars, all-仄韻) / 虞美人 (56 chars, alternating 平/仄韻) / 如夢令 (33 chars, single-strain 小令 with 二字疊句) / 西江月 (50 chars, 平仄通叶); strict character count + line-length sequence + rhyme positions + tonal pattern (平仄譜) all on-spec; faction tag [豪放派] vs [婉約派] declared and enforced; modern vocabulary (computer / coffee / metro) categorically banned, mapped to classical equivalents; five reference samples (Su Shi × 2 / Li Yu / Li Qingzhao / Xin Qiji) |

### Interpretive Rewriting (Lens)

A different axis from style skills — events stay; interpretation is rewritten. The skill rewrites the narrative's own framing of motive and meaning, so the text reads as if it were always seeing itself through that theoretical lens.

| Skill | Function |
|-------|----------|
| [psychoanalytic-lens](./psychoanalytic-lens/) | Rewrite narrative through Freudian/Lacanian psychoanalysis — preserves events, replaces surface motivations with their symbolic roots; strict school selection (no [F]/[L] cocktail mixing); three core clauses: event preservation / concepts arise naturally / substitute-narration mandate |
| [postmodern-lens](./postmodern-lens/) | Rewrite narrative through postmodern theory (Lyotard / Derrida / Foucault / Baudrillard / Jameson / Barthes / Kristeva) — mandatory metanarrative-doubt (narrator interjects to question its own narration / competing versions / writing the "how should this be told" into the narration itself); compatible school pairings ([D]+[B], [F]+[J], [L]+[Bd]) but no five-school pile-up; forbids "Derrida would say" cite-style sentences | [demo](./postmodern-lens/examples/demo.md) |

### Internet Vernacular

Subculture/meme styles amplified by recent social media: tautological echo, melodramatic headlines, complaint-as-flex, pseudo-academic gibberish. Each skill systematizes the meme's syntax into a checklist.

| Skill | Function |
|-------|----------|
| [feihua-literature](./feihua-literature/) | Rewrite into "feihua literature" (廢話文學, nonsense talk) — zero information density, three formulas (synonym substitution / self-contradiction / Q-keyword echo) at least two firing; Lu Xun's "one is a jujube tree, and the other is also a jujube tree" as literary precedent; viral on Weibo/Douyin in 2021 |
| [zhiyin-style](./zhiyin-style/) | Rewrite into Zhiyin-magazine style (知音體) — melodramatic headline (≥10 chars with stacked exclamations) + three-act tragic narrative (fated start / suffering middle / cathartic end) + density of tear/blood/love/fate keywords; the iconic Chinese magazine emotional-narrative style since 1985 |
| [versailles-literature](./versailles-literature/) | Rewrite into Versailles literature (凡爾賽文學) — humblebrag completely buried under complaint (false depreciation / self Q&A / third-party praise); originated from Weibo @小奶球 in 2020, popularized by 蒙淇淇77; academically defined as Chinese-social-media humblebrag genre |
| [concrete-42](./concrete-42/) | Rewrite into "spaghetti should be mixed with Type-42 concrete" style — pseudo-professional patter + cross-domain noun collage + serious-faced incoherence; satirizes evasion / jargon-stuffing / non-answers; originated from 卧龍鳳雛 (Bilibili) 2024 |

## Installation

### Ask Your AI to Install

Paste the following prompt to your AI assistant (Claude Code, Cursor, Windsurf, etc.):

```
Install the humanize skill from https://github.com/tzengyuxio/skills into my
global skills directory (~/.claude/skills/). Use git clone --depth 1, copy only
the needed skill folder, and clean up the temp files.
```

Replace `humanize` with any skill name. To install into the current project, change the path to `.claude/skills/`.

### One-Liner

```bash
git clone --depth 1 https://github.com/tzengyuxio/skills.git /tmp/tz-skills \
  && mkdir -p ~/.claude/skills \
  && cp -r /tmp/tz-skills/humanize ~/.claude/skills/ \
  && rm -rf /tmp/tz-skills
```

Replace `humanize` with any skill name, or list multiple (e.g. `dewesternise westernise`). To install into a project, change `~/.claude/skills` to `.claude/skills`.

### Plugin Marketplace

```
/plugin marketplace add tzengyuxio/skills
/plugin install humanize@tzengyuxio-skills
```

## License

MIT
