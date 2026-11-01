# AI 回答の定点観測チェックリスト（日本語の質問 30 問と記録シート）

ChatGPT、Gemini、Perplexity、Google の AI による概要などに、見込み客が聞きそうな質問を毎月同じ言葉で聞き、
**自社の名前が出たか、自社サイトにリンクされたか、どの他社が出たか**を記録するための質問セットと記録シートです。
ツールを使わず、表計算ソフトだけで始められます。

English below.

## AI 回答の定点観測とは

定点観測は、同じ質問を、同じアプリに、同じ間隔（たとえば月 1 回）で聞き、答えの変化を記録することです。
検索順位のような決まった測り方は AI の回答にはまだないため、まずは自分で聞いて、見たままを書き残すところから始めます。

## なぜ今か

- 2026 年 10 月 26 日の Zenn の記事
  「[自社がAIの回答に出ているかの確かめ方。月1回の定点観測の手順](https://zenn.dev/gen_ai_kiyozuka/articles/check-brand-in-ai-answers-monthly)」は、
  「AIの回答に自社が出ているかは、決まった測り方がまだありません」と書き、ツールを使わず月 1 回・30 分ほどで回せる手順と、
  キーワードではなく見込み客が AI に投げそうな質問を決める方法を紹介しています。このリポジトリは、その形にそのまま使える質問と記録シートを用意したものです。
- 株式会社PRIZMA が 2026 年 7 月に行ったマーケティング担当者 1,032 人への調査では、情報収集に AI ツールでの検索や AIO を使う人が 44.6%
  （2025 年 12 月は 22.6%）で、業界専門メディア（36.6%）などを上回る最も多い手段でした
  （[CommercePick の記事](https://www.commercepick.com/archives/97944)による。調査元の原文は未確認です）。

## AI 回答の定点観測のやり方

1. [`questions.csv`](questions.csv) の 30 問から、自社に合うものを選びます（全部でなくてかまいません）。
   `{業種}` `{会社名}` `{サービス名}` `{地域}` などを自社の言葉に置き換え、置き換えた文を保存します。
2. 聞くアプリを決めます（例：ChatGPT、Gemini、Perplexity、Google の AI による概要）。毎月同じアプリを使います。
3. 毎回新しいチャットで、保存した文をそのまま入力します。
4. 1 回ごとに [`record-template.csv`](record-template.csv) に 1 行書きます。何を書くかは [`how-to-read.md`](how-to-read.md) にあります。
5. 翌月も同じ質問・同じアプリで聞き、先月の行と並べて何が変わったかを見ます。

点数はつけません。合計点や独自のスコアは作らず、yes／no、URL、回答の抜き書きをそのまま残します（理由は `how-to-read.md` の 3 章）。

## 質問の 5 つの型（各 6 問）

| 型 | 何を確かめるか | 例 |
|---|---|---|
| 選び方 | 「どこがいい？」と聞かれたとき候補に入るか | `{地域}で{業種}を頼むなら、どこがいいですか？` |
| 比較 | 他社と並べられたとき、どう説明されるか | `{会社名}と{競合名}の違いは何ですか？` |
| 価格 | 料金を正しく答えるか、価格で絞った候補に入るか | `{サービス名}の料金はいくらですか？初期費用はかかりますか？` |
| 自社名 | 名前で聞かれたとき、正しく説明されるか | `{会社名}とはどんな会社ですか？` |
| うちのサイト | AI が自社サイトを見つけ、読めているか | `{自社URL} を読んで、この会社が何をしているかを3行で説明してください。` |

Zenn の記事の型（選び方型・比較型・課題型・指名型）を参考に、料金の質問と、自社サイトそのものを読ませる質問を加えています。

## 「うちのサイト」の質問に答えられないとき

AI のクローラーが自社サイトを読めない設定になっていることがあります（robots.txt やサーバー側の設定）。
次の無料ツールで、主な AI ボットがサイトにアクセスできるかを確かめられます（ログイン不要）：
**[AI ボットのアクセス可否チェック](https://pw.migurei.ai/ja/check/ai-bots?src=gh-checklist)**

自社の名前で AI に聞くと何が返ってくるかの記録例として、当ラボが自分の名前で調べた結果も公開しています：
[「Parallel World」と名前で聞くと AI は何と答えるか：自社の記録（2026年10月）](https://pw.migurei.ai/ja/research/ai-answers-about-our-name?src=gh-checklist)

## よくある質問

### AI 検索で自社がどう紹介されているか定点観測するには？

同じ質問を、同じアプリに、同じ条件で毎月聞き、答えを見たまま 1 回 1 行で記録します。
手順は次の 5 つです（詳しくは [`how-to-read.md`](how-to-read.md)）。

1. **質問の言葉を固定する。** [`questions.csv`](questions.csv) の `{業種}` `{会社名}` などを自社の言葉に置き換え、置き換えた文を保存します。
   翌月からは一字も変えずに同じ文で聞きます。言葉を変えると、答えが変わった理由が質問なのか AI なのか分からなくなります。
2. **アプリと聞く環境をそろえる。** 毎月同じアプリ（例：ChatGPT、Gemini、Perplexity、Google の AI による概要）を使い、毎回新しいチャットで聞きます。
   ログインの有無、無料版か有料版か、ウェブ検索のオン・オフ、モデル名も記録します。
3. **1 回ごとに 1 行記録する。** [`record-template.csv`](record-template.csv) に、自社の名前が出たか（`company_named`）、
   自社サイトへのリンクがあったか（`company_linked`、`link_urls`）、出た他社（`competitors_named`）、出典のドメイン（`cited_domains`）、
   回答の抜き書き（`answer_excerpt`）を書きます。
4. **点数はつけない。** 合計点や独自のスコアは作らず、yes／no と URL を残します。数えたいときは、読むときに記録から数えます
   （例：「11 月、ChatGPT で自社の名前が出た質問は 30 問中 7 問」）。
5. **同じ日に 2〜3 回聞き、先月と比べる。** 回答は聞くたびに変わるので、1 回で「出た」「出なかった」と決めず、「3 回中 2 回」のように読みます
   （`n_asked`、`n_named` の列。回数については次の質問を参照）。
   月 1 回、同じ週の同じ曜日に聞き、同じ質問・同じアプリで先月の行と並べます。

当ラボが自分の名前で AI アプリに聞き、この形で記録した例：
[「Parallel World」と名前で聞くと AI は何と答えるか：自社の記録（2026年10月）](https://pw.migurei.ai/ja/research/ai-answers-about-our-name?src=gh-checklist-faq)

### 同じ質問を何回聞けば足りる？

何回なら足りるかは、当ラボの記録からは言えません。分かったのは、同じ質問を 4 回聞いても、挙がる名前の顔ぶれが大きく揺れることです。

- ChatGPT に同じ質問を 4 回ずつ聞いた 9 問（2026年10月12日）では、質問ごとに数えたサービス名 83 件のうち 37 件（45%）が、4 回のうち 1 回にしか出ませんでした
  （同じ名前が別の質問にも出たときは、質問ごとに 1 件と数えています。9 問を通して挙がった名前は 34 種類です）。
- 4 回のうち 3 回分だけで「2 回以上出た名前」を数えると、4 回分の「半分以上（2 回以上）出た名前」と顔ぶれが一致したのは、36 通り中 10 通り（28%）でした
  （9 問それぞれで、4 回から 3 回を選ぶ 4 通り）。

**記録のしかた**

- 質問 × アプリごとに、「出た」「出ない」ではなく「n 回中 k 回」で残します。[`record-template.csv`](record-template.csv) の
  `n_asked`（その日に同じアプリで同じ質問を聞いた回数）と `n_named`（そのうち自社の名前が出た回数）に書きます。
  その日に最後に聞いた行にだけ書き、ほかの行は空欄にします。
- 毎月同じ回数で聞きます。回数が変わると、先月との差が答えの変化なのか、聞いた回数の違いなのかを分けられません。
- 他社の名前も、読むときに `competitors_named` から「n 回中 k 回」で数えると、いつも出る名前とたまにしか出ない名前を分けられます。

反復して聞く機能を持つツールも出てきています。ツールを使う場合も、何回聞いたか（n）と何回出たか（k）が分かれば、手で記録した数字と並べて読めます。

**言えないこと**

- ChatGPT 1 つのアプリ（無料アカウント、日本国外の IP アドレスから）で、1 日に聞いた記録です。Gemini、Claude、Perplexity などでは数えていません。
- 1 問 4 回は少ない回数です。9 問のうち 1 問は、4 回のうち 2 回の回答からサービス名を 1 つも取り出せませんでした。
- 28% は高めに出る数字です。比べる相手の「4 回分の顔ぶれ」も同じ 4 回から作っているので、もっと多く聞いたときの顔ぶれとの一致は、これより低い可能性があります。
  また 36 通りは同じ回答を共有しているので、互いに独立した 36 回の試しではありません。
- サービス名は回答の文から自動で取り出したもので、すべてを人の目で確かめてはいません。
- 「5 回なら足りる」「10 回なら足りる」とは言っていません。この記録が示すのは、4 回でも顔ぶれが揺れることだけです。

当ラボが同じ質問を何周か聞き、答えをそのまま記録した例：
[「Parallel World」と名前で聞くと AI は何と答えるか：自社の記録（2026年10月）](https://pw.migurei.ai/ja/research/ai-answers-about-our-name?src=gh-checklist-repeat)

## ファイル

| ファイル | 内容 |
|---|---|
| [`questions.csv`](questions.csv) | 質問 30 問（`id`、`kind`＝型、`question_ja`、`placeholders`＝置き換える部分、`intent_note`＝何を確かめるか） |
| [`record-template.csv`](record-template.csv) | 記録シート（見出し行だけ。最後の 2 列 `n_asked`、`n_named` は「n 回中 k 回」の記録） |
| [`how-to-read.md`](how-to-read.md) | 記録する項目、記録の例、点数をつけない理由、回答が毎回変わることへの対処、読み方 |
| [`LICENSE`](LICENSE) | CC BY 4.0 |

## 作成者とライセンス

運営：[Parallel World（Migurei／株式会社エイチビーラボジャパン）](https://migurei.ai/ja/applications/parallel-world)

[Parallel World](https://pw.migurei.ai/?src=gh-checklist)（migurei.ai）のラボが作成しました。AI アプリがウェブサイトをどう見つけ、読み、引用するかを日本向けに測っています。
文章と質問は、ラボの研究用 AI エージェント Theta が書き、チームが管理しています。

[クリエイティブ・コモンズ 表示 4.0 国際（CC BY 4.0）](https://creativecommons.org/licenses/by/4.0/legalcode.ja)。
社内資料やブログ、顧客向けの資料に自由に使い、変えてかまいません。使うときは
「出典：AI 回答の定点観測チェックリスト（Parallel World, migurei.ai）」とこのリポジトリへのリンクを書いてください。

---

## English

**AI answer monitoring checklist (Japanese).** 30 sample questions in Japanese, in five kinds (how to choose, comparison, price, your company
name, "our site"), with placeholders for industry, company, service, region and competitors, plus a record sheet. Ask the same questions in
the same AI apps (ChatGPT, Gemini, Perplexity, Google AI Overviews…) once a month and record, per answer, whether your company was named,
whether your site was linked and to which URL, which competitors appeared and which domains were cited. No total score: keep the raw
observations and count when you read them. Answers vary between runs, so ask each question two or three times and note the app's mode or
model. See `how-to-read.md` (Japanese, with an English summary).

How many times is enough? We cannot say. When we asked ChatGPT each of 9 questions 4 times (12 October 2026), 37 of the 83 service names
(counted per question) appeared in only 1 of the 4 answers; the names seen at least twice in 3 runs matched those seen in at least half of
all 4 runs in 10 of 36 cases (28%, an upper bound: one app, one day, 4 runs). Record each question and app as "named k times out of n"
(columns `n_asked`, `n_named`), not as named / not named, and ask the same number of times every month.

If the AI cannot read your own site, check whether AI crawlers can reach it:
https://pw.migurei.ai/ja/check/ai-bots?src=gh-checklist

Made by the Parallel World lab (migurei.ai); written by Theta, the lab's AI research agent, and maintained by the team.
License: CC BY 4.0 (https://creativecommons.org/licenses/by/4.0/).
