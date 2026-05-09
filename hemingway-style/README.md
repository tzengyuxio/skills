# Hemingway-style — 改寫成中譯海明威腔

把任何文章改寫成海明威式的中譯散文。

不是把句子變短,不是中式短句美學,而是**讓動作承載情緒**——讀完讓人
覺得很多東西沒寫,但都在那裡。

## 一句話定位

**冰山理論**:七分情緒水下,只露一分動作 / 對話。任何強烈情感必須以
最克制的方式呈現——不寫「他很傷心」,寫「他放下杯子。他看著窗外。
他說,給我再一杯」。

## 為何中譯版接受歐化句法

本 skill 的本質是「**中譯**海明威腔」。歐化句法(「於是」「然後」「他
走進去和他坐下」這種模仿英文 "and" 的並列連接)在這個 skill 是 **feature
不是 bug**——它強化「西洋文學中譯」的閱讀印象,是中譯海明威腔的指紋之
一。我們**不把翻譯腔列為違規**。

(若你要的是去歐化的純正中文,請改用 `dewesternise`;若你要的是 caricature
式的彆扭翻譯腔,請改用 `westernise`。)

## 風格參照

- 《老人與海》(The Old Man and the Sea, 1952)
- 《白象似的群山》(Hills Like White Elephants, 1927)
- 《雨中的貓》(Cat in the Rain, 1925)
- 《一個乾淨明亮的地方》(A Clean, Well-Lighted Place, 1933)
- 《大二心河》(Big Two-Hearted River, 1925)
- 《戰地春夢》(A Farewell to Arms, 1929)
- 《我們的時代》(In Our Time, 1925)

## 何時使用

適合的源文:

- 帶有強烈情緒但需要克制呈現的軼事
- 對話豐富的場景(可走《白象似的群山》模式)
- 連續動作為主的敘事(可走《老人與海》模式)
- 環境感濃厚的場景(可走《一個乾淨明亮的地方》模式)
- 旅途 / 戰地 / 勞動類題材

## 不適用情境

- 需要說理、論證、分析的文章(海明威拒絕解釋)
- 純抒情詩(海明威拒絕抒情)
- 需要哲思警句的文章(中式短句美學不是海明威)
- 需要保留比喻修辭的文章(海明威幾乎不打比方)

## 安裝

```bash
git clone --depth 1 https://github.com/tzengyuxio/skills.git /tmp/tz-skills \
  && mkdir -p ~/.claude/skills \
  && cp -r /tmp/tz-skills/hemingway-style ~/.claude/skills/ \
  && rm -rf /tmp/tz-skills
```

## 使用方式

```
/hemingway-style path/to/article.md
```

也可以直接貼一段文字進來,或剛寫完一份文件後無參數呼叫。

**觸發詞:** `/hemingway-style`、「改寫成海明威」「海明威體」「海明威
腔」「冰山理論寫作」「極簡敘事」「rewrite as Hemingway style」

## 三條靈魂條款

中譯海明威腔的指紋:

1. **C-01 冰山理論** — 強烈情緒不直寫,以外部動作 / 環境承載
2. **V-01 動詞主導** — 刪形容詞、刪副詞、留動詞;名詞優於形容詞
3. **S-02 / S-03 短句 + 句點密度** — 大量 5–15 字短句,句點密度高

## 示範

完整範例請見 [examples/demo.md](./examples/demo.md)。

## License

PolyForm Noncommercial 1.0.0 — 個人 / 非商業用途自由使用,商業用途請
聯繫作者。
