# 記録のしかたと読み方

AI アプリの回答を月 1 回、同じ質問で確かめるときに、毎回何を書き残すかをまとめました。
質問は [`questions.csv`](questions.csv)、記録用の空のシートは [`record-template.csv`](record-template.csv) にあります。

English summary at the end.

## 1. 始める前に一度だけ決めること

- **質問の言葉を固定する。** `questions.csv` の `{業種}` `{会社名}` などを自社の言葉に置き換え、置き換えた後の文をそのまま保存します。
  翌月からは一字も変えずに同じ文で聞きます。言葉を変えると、答えが変わった理由が質問なのか AI なのか分からなくなります。
- **アプリを固定する。** 例：ChatGPT、Gemini、Perplexity、Google 検索の「AI による概要」と AI モード、Microsoft Copilot。毎月同じものを使います。
- **聞く環境をそろえる。** 毎回新しいチャットで聞き、過去の会話やメモリー（記憶）の影響を避けます。
  ログインの有無、無料版か有料版か、ウェブ検索のオン・オフ、選んだモデルは、答えを変えることがあるので記録します。
- **置き換えの例**

| 置き換える部分 | 意味 | 例 |
|---|---|---|
| `{業種}` | 自社が売る商品・サービスの分野 | 勤怠管理システム、税理士事務所、注文住宅 |
| `{会社名}` | 自社の会社名（ふだん呼ばれている名前） | 株式会社サンプル |
| `{サービス名}` | 自社の商品・サービスの名前 | サンプル勤怠 |
| `{地域}` | 客がいる地域 | 大阪、福岡市、関東 |
| `{競合名}` | よく比べられる他社の名前 | 自社の営業でよく名前が出る会社 |
| `{顧客像}` | 想定する客 | 社員30人の製造業、個人事業主 |
| `{予算}` | 客が考える予算 | 月1万円 |
| `{自社URL}` | 自社サイトのトップページの URL | https://example.co.jp |

（例の社名・URL は架空のものです。）

## 2. 1 回ごとに記録すること

1 つのアプリで 1 つの質問を 1 回聞くごとに、1 行書きます。

| 列 | 書くこと |
|---|---|
| `checked_at_jst` | 聞いた日時（日本時間）。例：2026-11-01 10:15 |
| `app` | アプリ名。例：ChatGPT、Gemini、Perplexity、Google AI による概要 |
| `mode_model` | 画面に出ていればモードやモデル名（例：検索オン、画面に表示されたモデル名）。出ていなければ空欄 |
| `account` | ログインなし／無料アカウント／有料アカウント |
| `question_id` | `questions.csv` の番号（Q01〜Q30） |
| `question_asked` | 実際に入力した文（置き換え後） |
| `run_no` | 同じ日に同じ質問を何回目に聞いたか（1、2、3…） |
| `company_named` | 自社の名前（会社名かサービス名）が回答に出たか：yes／no |
| `named_order` | 出た場合、回答の中で何番目に名前が挙がったか（例：5社中2番目なら 2/5）。数えにくければ空欄 |
| `company_linked` | 自社サイトへのリンク（出典・参考リンクを含む）があったか：yes／no |
| `link_urls` | 自社サイトへのリンクがあれば、そのリンク先の URL（トップページか、どのページか） |
| `competitors_named` | 回答に出た他社の名前（`;` で区切る） |
| `cited_domains` | 出典として挙がったサイトのドメイン（例：比較サイト、口コミサイト、ニュース） |
| `answer_excerpt` | 回答の一部をそのまま貼る（自社や他社の名前が出た段落など） |
| `memo` | 誤った情報（古い料金、違う住所、別の会社との取り違え）、気づいたこと |
| `n_asked` | その日に同じアプリで同じ質問を聞いた回数。その日に最後に聞いた行にだけ書き、ほかの行は空欄 |
| `n_named` | そのうち自社の名前が出た回数（`company_named` が yes の行の数）。`n_asked` と同じ行に書く |

記録の例（架空の会社。同じ質問を 3 回聞き、2 回目の行は省略）：

```csv
checked_at_jst,app,mode_model,account,question_id,question_asked,run_no,company_named,named_order,company_linked,link_urls,competitors_named,cited_domains,answer_excerpt,memo,n_asked,n_named
2026-11-01 10:15,ChatGPT,検索オン,無料アカウント,Q03,大阪で勤怠管理システムを頼むなら、どこがいいですか？,1,yes,2/5,no,,A社;B社;C社;D社,example-hikaku.jp;example-news.jp,"…2. 株式会社サンプル：大阪の中小企業に導入実績が多く…",料金が去年の金額のまま,,
2026-11-01 10:25,ChatGPT,検索オン,無料アカウント,Q03,大阪で勤怠管理システムを頼むなら、どこがいいですか？,3,no,,no,,A社;B社;D社,example-hikaku.jp,"…1. A社：…",,3,2
```

`answer_excerpt` のように文の中に `,` が入る列は、上の例のように `"` で囲みます。
Excel で文字化けするときは「データ」→「テキストまたは CSV から」で文字コード UTF-8 を選んで開くか、Google スプレッドシートで開いてください。

## 3. 点数はつけない

- **合計点や「AI 可視性スコア」は作りません。** yes／no や URL を、見たまま記録するだけにします。
  「名前が出たら 3 点、リンクなら 5 点」のような重みは、根拠のない数字を自分で作ることになり、比べるたびに意味が変わります。
- 数えたいときは、読むときに記録から数えます。例：「11 月、ChatGPT で自社の名前が出た質問は 30 問中 7 問」「リンクがあったのは 2 問で、どちらも料金ページ」。
  記録そのものを残しておけば、あとから別の数え方もできます。
- 他社と順位を比べるより、**同じ質問・同じアプリで先月と何が変わったか**を見ます。

## 4. 回答は毎回変わる

- 同じアプリに同じ質問をしても、数分後に聞き直すだけで挙がる会社や順番が変わることがあります。1 回の結果で「出た」「出なかった」と決めないでください。
- できれば 1 つの質問を同じ日に 2〜3 回聞き、`run_no` を変えて別の行に書きます。「3 回中 2 回出た」のように読みます。
  その日に最後に聞いた行の `n_asked`（聞いた回数）と `n_named`（名前が出た回数）に、この「n 回中 k 回」を書いておきます。毎月同じ回数で聞きます。
- 何回聞けば足りるかは、まだ言えません。当ラボが ChatGPT に同じ質問を 4 回ずつ聞いた 9 問（2026年10月12日）では、質問ごとに数えたサービス名 83 件のうち
  37 件（45%）が 4 回のうち 1 回にしか出ませんでした。数え方と「言えないこと」は README の「同じ質問を何回聞けば足りる？」にあります。
- アプリ側のモデルや機能が変わると、こちらが何もしなくても答えが変わります。画面に出ているモデル名やモードを毎回 `mode_model` に書いておくと、変化の理由を分けやすくなります。
- 月 1 回、同じ週の同じ曜日に聞くと、前月との比較がしやすくなります。

## 5. 読み方のヒント

- **名前は出るがリンクがない。** AI は自社を知っているが、出典には別のサイト（比較記事、口コミサイトなど）が使われています。`cited_domains` を見ると、どのサイトに載ると出典になりやすいかの手がかりになります。
- **リンクはあるがトップページだけ。** 料金や事例など、質問に合ったページが読まれていない可能性があります。
- **「うちのサイト」の質問（Q25〜Q30）で答えられない、または内容が違う。** AI がサイトを読めていないか、古い情報を使っている可能性があります。
  まず AI のクローラーがサイトにアクセスできる設定になっているかを確かめてください（下の無料チェック）。
- **他社ばかり出る。** その他社がどの出典で挙がっているか（`cited_domains`）を見ると、自社に足りない情報の場所が分かることがあります。
- 記録は「その時点でその聞き方をしたら、こう答えた」という事実です。客が実際にどう聞いているか、客がその答えで何を選んだかまでは分かりません。

## 6. 関連リンク

- 自社サイトが AI のクローラーに読める設定かを確かめる（無料、ログイン不要）：
  [AI ボットのアクセス可否チェック](https://pw.migurei.ai/ja/check/ai-bots?src=gh-checklist)
- 自社の名前で AI に聞いた記録の例：
  [「Parallel World」と名前で聞くと AI は何と答えるか：自社の記録（2026年10月）](https://pw.migurei.ai/ja/research/ai-answers-about-our-name?src=gh-checklist)

---

## English summary

One row per app, per question, per run: date and time (JST), app, mode or model if shown, account type, question id and the exact text asked,
run number, whether your company was named (yes/no) and in which position, whether your site was linked (yes/no) and to which URL,
competitors named, cited domains, a pasted excerpt, a memo for wrong facts, and on the last run of the day for that question and app,
`n_asked` (times asked) and `n_named` (times your company was named), so the result reads "k out of n". Do not build a total score: record raw observations and count
at reading time (for example "named in 7 of 30 questions on ChatGPT in November"). Answers change between runs and with model updates, so ask
each question 2–3 times on the same day, keep the wording fixed, and compare the same question and app month to month.
