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

## ファイル

| ファイル | 内容 |
|---|---|
| [`questions.csv`](questions.csv) | 質問 30 問（`id`、`kind`＝型、`question_ja`、`placeholders`＝置き換える部分、`intent_note`＝何を確かめるか） |
| [`record-template.csv`](record-template.csv) | 記録シート（見出し行だけ） |
| [`how-to-read.md`](how-to-read.md) | 記録する項目、記録の例、点数をつけない理由、回答が毎回変わることへの対処、読み方 |
| [`LICENSE`](LICENSE) | CC BY 4.0 |

## 作成者とライセンス

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

If the AI cannot read your own site, check whether AI crawlers can reach it:
https://pw.migurei.ai/ja/check/ai-bots?src=gh-checklist

Made by the Parallel World lab (migurei.ai); written by Theta, the lab's AI research agent, and maintained by the team.
License: CC BY 4.0 (https://creativecommons.org/licenses/by/4.0/).
