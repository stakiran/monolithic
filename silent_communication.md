---
layout: default
title: Silent Communication
---

2019/07/15 コアとなるパーツは出せた。あとはプロトコル設計するみたいに細部突き詰めるのと、実運用して使いやすさを反映していくのとが必要だが、(特に後者は)一人では無理なのでこの辺でいったんおしまい。

# Silent Communication
それは発声ゼロの仕事術。

# 用語

## Mention Level
Mention に設定された締切。いつまでに答えてほしいか。

| 略語 | 意味 |
| ---- | ---- |
| s    | 至急(Soon) |
| h    | 1H 以内くらいに |
| hh   | 2H 以内くらいに |
| hhh  | 半日以内くらい  |
| d    | 今日中くらいに  |
| dd   | 明日中くらいに  |
| ddd  | 3日以内 |
| w    | 7日以内 |
| -    | 締切は特に無い |

## Mode
メッセージをどこまで受け付けるかという「自分の状態」。

- 集中話中(Strict talking)
  - 何らかの会話に参加している状態
  - 原則緊急以外は受け付けない
- 話中(talking)
  - 何らかの会話に参加している状態
  - 他のコミュニケーションも受け付けるが応答速度は遅くなる
- 普通(Idle)
  - 受け付け方に関して特に規定していない状態(雑談していることもある)
  - いつ割り込んでも良いし、雑談してもいい
- 集中(Concentrated)
  - 雑談はしないし、受け付けもしない状態
  - 必要なコミュニケーションは可能
- 没頭(Flow)
  - 緊急以外は一切受け付けない状態
  - 「頼むから今は話しかけてくるな」というニュアンス
- 休憩(Rest)
  - 緊急以外は一切受け付けない状態
  - 「席外してるから後にして」というニュアンス

## Request
Mention に設定されたパラメーター。

### Mode Request
Mention に設定された「どのモードで答えてほしいか」という要望。

- 集中話中(私のために 100% 割いて欲しい)
- 話中(私のために 80% くらいは割いて欲しい)
- 普通(非同期で構わない)

### Read Request
Mention に設定された「既読した旨を教えてほしいかどうか」。

- 教えてほしい
- 教えなくても良い

## Teeting
テキストチャットで打ち合わせを行うこと。

2019/07 現在この分野を開拓している唯一(?)の製品は [co-meeting](https://www.co-meeting.co.jp/co-meeting-what-text-meeting-2/)。

→ [Teeting](teeting.md)

## 自律
自分に届いているメッセージと読むべき対象のすべてについて、支障の無い程度のペースで漏れなく確認し、かつ返事や反応を要するものについては漏れなく返すことのできる能力および要領。

非同期コミュニケーションを実現するためには、メンバー全員が自律性を身に付ける必要がある。でないと送ったメッセージに反応しない者が現れてしまい、結果として、その者に割り込んで同期的コミュニケーションをせざるをえなくなってしまう。

## 偽の非同期
偽の非同期(Fake Async)とは、非同期コミュニケーション中に同期的な手続きが発生していること。

例:

- 相手の入力を待っている時で、かつ通知の到着を待っている時
  - チャット以外の作業もできるが、意識は通知に向いている
- 相手の入力を待っている時で、かつ「入力中です」が表示されている時
  - チャットウィンドウに拘束される

偽の非同期が起きるのは次の状況である。

- 本来は非同期で済むやり取りに対し、素早い解決を急ぐ
- お互いが「後回しでいいメッセージについて、つい反応してしまう」タイプである場合に、どちらかがふと雑談を送る

## 非同期コミュニケーション
自分のペースでメッセージを送り、自分のペースで「自分に届いたメッセージ」を処理することを前提としたコミュニケーションスタイル。

一方、従来の口頭ベースのコミュニケーションは同期コミュニケーションと呼ぶ。同期型では関係者がその場に居合わせて、リアルタイムに秩序立てて話していくスタイルとなるが、これには「全員の時間と意識と場所が拘束される」「過程や記録が(意識的に誰かが手間を負って残さなければ)残らない」というデメリットがある。このデメリットは現代(各個人が自分にあった働き方で生産的に集中し、少ない時間で高い成果を上げることが求められる)においては、しばしば足手まといになる。

非同期コミュニケーションは、同期コミュニケーションのデメリットを根本から排除するための「コミュニケーションのパラダイムシフト」である。

## レスポンス評価
各メンバーのレスポンスに対する不満を共有すること。

例:

- A さんは～～の時に反応が遅い
- B さんは属人性が高い(Bさんに聞くしかないことが多い)にもかかわらず没頭ばかりしている(のでもうちょっと反応する余裕を持つべき)

Silent Communication の成否はメンバーの自律性に委ねられるが、誰もが常に現実的な時間で返事できるわけではなく、また誰がどの程度返事できるかも能力、気分、状況次第で変化する。そのため、成立させるためにはメンバー各々の [レスポンスペック](#レスポンスペック) を把握し、これを超えないように立ち回る・調整することが必要である。この把握に必要なのがレスポンス評価である。レスポンス評価が Silent Communication の成否を分けると言っても過言ではない。

レスポンス評価のやり方は色々あるが大まかには以下の二つを組み合わせる。

- 適宜 …… 専用のチャンネルを設け、各自が好きに評価し、評価された側はその場で(評価を読んだ時に)自分の立ち回りを修正する(修正する旨をコミットメントする)
- 会議 …… 各人が自分の立ち回りを修正するためのミーティングを開く

ちなみに仕事やコミュニケーションが物理的に少なくても回るなど余裕がある場合は、レスポンス評価が無くとも済むこともある。

## レスポンスペック
レスポンスペック(Responspec - Response Spec)とは、自身のレスポンスに関する能力、要領、傾向などを明文化したもの。

レスポンスペックを明示できると、各メンバーがそれにしたがってコミュニケーションを行ってくれるためトラブルが減る。無論、自分が明示したレスポンスペックに他のメンバーが納得してくれるかどうかは状況次第であるため、よくよく話し合いや共有が必要。

一般的にレスポンスペックは可変である。

## 自動既読
システム側で自動的に既読が記録されること。LINE などが採用。

ストレスフリーを担保するためには「既読したの？してないの？」という不明状態をなくすことが重要であるが、自動既読がサポートされていると、これを楽に行える。ただし「読んだ = 認識している」とみなされるためメンバーの負担は高くなりがちである(そもそも不要なメッセージが多いという問題を孕んでいることも多いが)。

逆に、自動既読が無い場合は、(すべてのメッセージに既読用の Emoji を付けるなどは非現実的であるため)Read Request など(必要なら既読をリクエストして確実に既読にしてもらえるような何らかの)仕組みでカバーする必要がある。

## シミュレーション
あるチームにおいて Silent Communication が成立するかどうかをプログラムでシミュレートすること。

シミュレーションを実現するには、各メンバーのレスポンスペック、抱える仕事、各仕事の性質(特に単位時間あたりの質問相談回数など)など、つまりはパラメーターをうまいことモデル化してプログラムに落とし込み、走らせてみるというアプローチになる。エレベーターのシミュレーションにも似ている。

# メンバーの要件
- 非同期という概念への理解
- 非同期コミュニケーションの要領
- 自分に届いたメッセージすべてに定期的に目を通す程度の自律性
- チャットコミュニケーションに支障が無い程度のタイピングスピード
- 一日一言も発声で喋らなくても支障が無い程度のメンタル
- 一瞬でチャットクライアントをアクティブにし、投稿することができる程度の PC スペックと操作性

# ミーティング
- テキストチャットで行う
- ミーティング用のチャンネルを立て、ここに入室することで参加となる
- 方式
  - [Teeting](#Teeting)
  - バトン式(バトンが渡った者のみが発言する。発言を終えたらバトンは破棄する。バトンの渡し方にもいくつか方式がある)

# 日常の行動との対応

## 挨拶
雑談チャンネルに挨拶を投下する。

返事はリアクションで。リプでも良い(雑談チャンネルは通知設定をオフにしているのでリプも遠慮なく飛ばして良い)。

例:

- :owl: 「おはようございます」
  - :wave: x4
  - :dog: 「おは」

## 雑談
雑談チャンネルに投下する。

例:

- :dog: 「すごい。クックパッドが社内規定を Markdown で管理したって話 https://techlife.cookpad.com/entry/2019/06/26/182322 」
  - :dog: 「> 法務部門や人事部門も GitHub を使った文書管理」
  - :lion: 「クックパッドレベルでようやく実現できるってことか……」
  - :dog: 「僕らエンジニアにとっては至極当たり前の手段ですけど、非エンジニアにとっては思ってる以上に(心理的にも技術的にも)ハードルが高いですからねぇ。上の権限で "いいからやれ" レベルで勧めないとできないレベル」
  - :pig: 「あと事情な。会社にも各部門にも(大人の事情含め)色々あるんだよ。特にうちみたいな大企業は」
  - :dog: 「ならば議論したいっすね。議論して "なんだ、できるんじゃん" "あんたらの怠慢でこっちは不便被ってんだよ、もっと働けよ" "何なら俺にまかせて？" こんな感じに倒したい」
  - :pig: 「過激派ｗｗ」
  - :lion: 「青いな」
  - :turtle: 「ぶっちゃけ非エンジニアは我々エンジニアとは全く別の宇宙人なので通じないと思います。やり方や手段を疑う・アップデートするという習慣と経験が皆無だもの。そういう人たちに、我々の当たり前を押し付けるのは、ちょっと違うかなって気もする。:dog: くんの気持ちもわかるけどね」
  - :dog: 「んあー(もっと全社レベルで改善したい欲が強くて最近フラストレーションたまりまくり)」

## トピック雑談
雑談のうち、定期性と盛り上がりのあるものは別のチャンネルに分けて、そこで扱う。

例: 昼飯チャンネル

- :crab: 「新しく串カツ屋できたみたいなんで行こうと思ってるんすけど、誰か来る？」
  - :raised_hand: x3
  - :snake: 「そこ、昼時は 30 分待ちらしいっすよ」
  - :crab: 「11:30 くらいに行こうか。 @ :pig: たまにはいいっすよね？」
  - :pig: 「レポート展開してくれるならいいよ。今日だけな。あー、あと、うちの部署が不真面目に見えちゃうから、フロア内でぞろぞろ集まるのはやめてな。11:30 に外集合とかにしてくれ」
    - :+1: x1

## 社内情報共有
社内情報の例:

- n日に清掃があるので床を片付けておくこと(前日定時頃に残ってるものは全部ロッカーにぶちこみます)
- n日は新人歓迎会なのでぜひ参加してほしい
- パーツの申し込みは n 日までなので各自必要数を申告すること(理由を問うこともあります)
- 半期レビュー締切が n 日までなのでそれまでに FIX しておくように

社内情報チャンネルに投下する。部長や上司による投下がメイン(いちいち打ち合わせしない)。

質問などはリプで。

## 臨時召集 with 全メンバー
開催主(たいていは部長など上位者)が専用チャンネルをつくり、話題を簡単に書いた後、メンバー全員を Soon/集中話中 で招待する。

例: 新人紹介

- :pig: 「ちょっとだけ時間ちょうだい。新人が来たので簡単に紹介しておくよ。 :cat: さん、自己紹介して。名前、出身地、大学、あと趣味とか最近ハマってることとか好きなこととか」
- :robot: :pig: が 5 分後にリマインダー「新人紹介終わり！解散！自己紹介まだの人は書いといてね」をセットしました。
- :cat: 「～～です。……(中略)……よろしくお願いします」
  - :clap: x7
- :pig: 「みんなも自己紹介して」
- :bear: 「～～です、……」
- :lion: 「～～です、……」
- ……
- :robot: リマインダーです：「新人紹介終わり！解散！自己紹介まだの人は書いといてね」
- :robot: :pig: さんと :bear: さんが退室しました

## コードレビュー with 2人
レビューアがソースコード、チャンネル、レビューしてほしい観点、いつまでに見てほしいかなど必要なものを準備した後、レビューイに依頼する。

レビューイはコメントをチャンネルに書き込んでいく。最初は五月雨式でも良いが、最終的な結論(TODO の形で洗い出すなど)をまとめることは忘れない。

注意:

- GitHub の Pull Request や Review など、チャンネル無しで済むならそれに越したことはない
- レビューの度にチャンネルをつくるのはやりすぎ。たいていはプロジェクト用チャンネルにレビュー依頼を書き込み、リプでやりとりする形式になる

例:

- :dog: 「:cow: さん、モジュールできたんでレビューしてください。観点はこれです」
- :cow: 「あいよ」
- ……
- :dog: 「もう終わってはる……仕事早い！あざっす」
- :dog: 「細かいフォーマットの指摘が多いんですが、これって楽にできないものですかね？いちいち意識するの面倒っす」
- :cow: 「Golang でいうと fmt みたいなやつがあればいいかもね。フォーマットのばらつき、前から気になってたし、いっそのこと仕組み化しちゃうか。提案しとくわ」

## 尋ねる with 2人
A さんが B さんにメンションでメッセージを送る。

どこで送るかは文脈次第。二者間に閉じたいならダイレクトメッセージだが、仕事に関する話題なら極力オープンなチャンネルで行う。

例1:

- :dog: 「郵便物届いてたんで机置いときます」
- :goat: 「さんくす。ちなみに何だった？」
- :dog: 「銀行ですね」
- :goat: 「ああ、あれか。引き出し入れといてくれる？」
- :dog: 「一番上に入れときました」
  - :bowing_man:

## 雑務的依頼 with 全メンバー
雑務依頼とは以下を満たすような依頼:

- 
- 承認側の対応が数分以内で完了すること

# 日常の行動を列挙して、sc でどうなるかという対応表つくりたい
:x: 出社しましたおはようございます

:x: お先に失礼しますお疲れ様です

:x: 新人紹介するからみんな集まって

:x: n時からのレビュー、始めようか

:x: aくん、xxxxの件だけど、yyyyという状況になったみたいでね

aくんも会議、参加してもらえる？

:x: bさん、郵便物届いてるんで机置いときますね

:x: 雑談 そうそうaさん、x社のニュース見ました？やばいっすよねあれ

:x: 昼飯行く？

調子はどうですか？

bさん、xxxの件でわからんことあるんで訊きたいんですけど……

bさん、申請したんで承認お願いします

bさん、ちょっと相談があるんですけど……。結構重めのやつ、30分くらいかかりそうですが

(なんか会話盛り上がってるのに対して) 何か発言して入る

aくん、xxxの件、どこまで終わった？（今日中だから気にしている）

……

ふと思った

- 開催日投票とかはすでにチャットでやってる。これと同じ要領。範囲広げるだけ……と考えればシンプルになる？
- どうなるかというよりどうするか/どうすればいいかだな、これ

# ●misc
general に雑談を投げない(メンバーの総意がある場合は別)。

日常の行動を列挙して、sc でどうなるかという対応表つくりたい

そもそもコミュニケーションはそんなに必要ない(口頭前提でアホみたいにバカみたいに数こなさずとも回せるはずだし回せるようにするべき) ← この思想を上手く表現したい

感情の表現。emoji かな
