---
title: "Claude Codeで雑務を45個自動化！東大院生の全記録"
date: 2026-04-20T07:34:32+09:00
draft: false
categories: ["tech"]
tags: ["claude code", "業務効率化", "自動化", "ai活用", "プログラミング", "生産性向上", "エンジニアリング"]
slug: "claude-code-45-"
---

「またこのメールの返信か…」「似たような事務作業で一日が終わる…」

パソコンの前に座っているのに、気づけば「作業」に追われ、肝心の研究や創作に手がつけられない。そんなフラストレーションを感じたことはありませんか？

いまIT界隈で、東大大学院生のshunyaさん（@shunya_sudo）がZennで公開した**「Claude Codeで日常のタスクを45個自動化した東大院生の全記録」**という記事が話題です。彼は半年かけて、なんと**45個もの「面倒な雑務」を自動化**してしまいました。正直、ここまでやりきると一種の清々しさすらありますよね。

「なぜわざわざそこまで？」と思うかもしれません。メールの仕分けならツールでも十分ですから。ただ、彼の実践には私たちが明日から真似できる「自動化の極意」が詰まっています。

## 東大院生の執念：半年間の全記録

![Simple cartoon illustration: A clean infographic showing a bar chart with 45 bars, a clock showing "1 hour saved", and a glowing icon representing a personal backend server.](/images/claude-code-45-_0.png)

まずは、このプロジェクトがどれほど本格的なものか、数字で見てみましょう。

*   **自動化したタスク：** 45個
*   **開発期間：** 6ヶ月
*   **スクリプト数：** 132本
*   **AIエージェント数：** 36個
*   **運用コスト：** 月額100ドル（Claude Code Max料金）
*   **浮いた時間：** 1日あたり30分〜60分

彼が作ったのは、単なる「ショートカット」ではありません。Gmailの監視、arXivの論文通知、Discordの履歴からToDoを抽出する仕組み、さらには日程調整の返信ドラフト作成まで。これらをmacOSのcronで自動的に回す、本格的な「個人用バックエンド」です。ここまで来ると、もはや執念ですね。

## なぜ「AI」を使う必要があるのか？

![Simple cartoon illustration: A split screen. Left side: A simple arrow sorting paper into folders. Right side: A friendly robot character analyzing a document with a magnifying glass and a lightbulb icon.](/images/claude-code-45-_1.png)

「Gmailのラベル分けなんて、既存のフィルター機能で十分じゃない？」そう思うのも当然です。正直、私も最初はそう思っていました。

でも、shunyaさんがわざわざAIを組み込んだのには明確な理由があります。

それは、**「判断（思考）」が必要なタスクを自動化するため**です。

### 作業 vs 判断

![Simple cartoon illustration: A flowchart comparing "Old Way" (a simple filter funnel) vs "AI Way" (a thinking robot head taking data in, weighing options, and outputting a calendar invite).](/images/claude-code-45-_2.png)

*   **従来のフィルター：** 「〇〇さんからのメール」を「フォルダA」に入れる。ただの仕分けです。
*   **今回の自動化：**
    1.  **取得：** PythonでAPIを叩いてデータを引っぱる。
    2.  **判断：** Claudeが中身を読んで「返信が必要か」「タスクか」「読むだけでいいか」を分類。正直、この「仕分け」ができるだけでメール作業は別物になります。
    3.  **アクション：** 返信が必要なら、カレンダーの空き状況を見て候補日を添えた返信案を作成。

単にメールを分けるのではありません。**「自分ならどう判断するか」という思考をAIに叩き込み、返信まで完結させています。** こうなると、雑務は「発生した瞬間、気づけば終わっている」という夢のような状態になります。

## 成功を支えた3つの戦略

![Simple cartoon illustration: Three floating icons in a row: 1. A notebook labeled "Rules", 2. A heart icon floating next to a prompt box, 3. A shield icon with a checklist representing error protection.](/images/claude-code-45-_3.png)

彼が単なる「趣味の自動化」で終わらせず、実用的なシステムまで作り上げられたのには、外せない3つのルールがありました。

### 1. `CLAUDE.md`でAIを「教育」する
AIを思い通りに操るために、`CLAUDE.md`や`SKILL.md`といったファイルへプロジェクトのルールを叩き込んでいます。ただし、150〜200行を超えるとAIは指示を忘れます。いわゆる「Lost in the Middle」問題ですね。これを避けるため、ルールは徹底的に凝縮するのがコツです。

### 2. プロンプトに「感情」を混ぜる

![Simple cartoon illustration: A text bubble with a prompt saying "This is urgent!" and a heart symbol. A robot receives it and a "100% Quality" stamp appears next to the robot's head.](/images/claude-code-45-_4.png)

AIの回答精度を上げるために、「これは私のキャリアにとって極めて重要です」といった**「EmotionPrompt」**を使っています。単なる論理的な指示だけでなく、AIに文脈の重み付けをさせることで、ハイクオリティな回答を引き出せるんです。正直、この一手間だけで返答の質が驚くほど変わります。

### 3. 「壊れにくい」システム設計

![Simple cartoon illustration: A network of interconnected glowing nodes with a monitor showing a green "Success" checkmark, and a red alert signal going to a mobile device.](/images/claude-code-45-_5.png)

45個ものジョブが動いていれば、必ずどこかでエラーは起きます。だからこそ、彼は最初から「エラー通知」の仕組みを組み込みました。

Slackには専用チャンネルを12個も作り、異常があれば即座に通知が飛ぶ仕組みです。どこで何が起きたか一目でわかる。これ、運用する側からすれば本当に助かる設計ですよね。

## 自動化が生み出す「差」

![Simple cartoon illustration: A balance scale. On the left, a small pile labeled "Shallow Work." On the right, a massive, glowing pile labeled "Deep Work" (Research & Strategy).](/images/claude-code-45-_6.png)

読者からの反響は二極化しています。「今の採用市場は、院生レベルでもここまでやらないと生き残れないのか」という恐怖。一方で、「作る過程で得られる学びこそが本質だ」という賞賛の声です。

正直、月額15,000円というコストは決して安くありません。でも、「1日1時間の『深い集中時間』を毎日買っている」と考えたらどうでしょう。

*   **雑務（Shallow Work）：** メール、日程調整、情報収集。
*   **深層業務（Deep Work）：** 研究、コーディング、戦略立案。

彼にとっての100ドルは、雑務を切り捨てて「深層業務」に没頭するためのチケットなんです。これ、自己投資としてはかなり賢い選択だと思いませんか？

## 今日からできること

![Simple cartoon illustration: A roadmap starting with "5-minute task" (a small gear), leading to "Slack Notification" (a phone icon), and finally "Automated System" (a rocket ship).](/images/claude-code-45-_7.png)

全員に「132本のスクリプトを書け」なんて無茶は言いません。でも、この記録から盗めるヒントは確実にあります。

1. **「毎日5分以上かかる作業」を書き出す**
「毎日やっているけれど、考えなくても終わる作業」が一つくらいあるはずです。まずはそこを見つけましょう。

2. **まずは「通知」から始める**
いきなり自動返信させるのは怖いですよね。なら、最初は「要約をSlackに飛ばす」だけで十分。これだけでメールを開くたびに感じるあの重苦しさが消えます。正直、これだけでQOLが爆上がりします。

3. **「5分で作れるもの」から手を出す**
最初から壮大なシステムを組む必要はありません。「特定のメールが来たらSlackに通知する」くらいの小さな自動化から始めてください。

4. **「失敗」を仕組みでカバーする**
スクリプトが止まったら通知が届くようにしておけばいいんです。これだけで「自動化＝怖い」という不安は消し飛ぶはず。

自動化って、結局は「自分の時間の使い方」を設計することなんですよね。

![Simple cartoon illustration: A person sitting at a desk, looking relaxed at a sunset through a window, while a small robot friend clears away the last few papers from the table.](/images/claude-code-45-_8.png)

shunyaさんの記録が教えてくれるのは、単なるエンジニアリングの凄さじゃない。**「自分の時間を何に使うか自分で決め、不要なものはバッサリ捨てる」という強い意思**だ。

日々の雑務に追われているのは、あなたの能力が低いからじゃない。単純に**「仕組み」が整っていないだけ**だ。正直、僕も昔はタスクに埋もれて毎日ヒーヒー言っていた。

まずは「5分で終わる作業」を一つ選んで、今すぐ自動化してみよう。その先にこそ、あなたが本来やるべき「濃い時間」が待っているはずだ。