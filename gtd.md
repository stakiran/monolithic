---
layout: default
title: GTD
---

# Height
高度(Height)とは GTD ユーザーの行動に一貫性をもたせるための観点。高い高度(価値観や理想など抽象的な軸)をもとに、低い高度(具体的な行動内容)をつくっていくというアプローチを取る。

## Overview
- 5000m Philosophy(譲れない価値観)
- 4000m Ideal(手に入れたい/維持したい理想)
- 3000m Milestone(1-2年後に達成したいこと)
- 2000m Restrictions(現在抱えている制約)
  - 責任を負っているもの
  - 直近注意を向けなければならない(not WANT, not SHOULD, but MUST)もの
- 1000m Project
  - 2000m から生じる必須タスク
  - 3000m の達成に必要な小目標
  - その他細々とした雑事のうち、Nextaction ほど今すぐではないが Someday ほど放置したくないもの
- 0000m Nextactions
  - デイリータスクリスト
  - カレンダー
  - リマインダー

# Workflow
Workflow(ワークフロー)とは GTD 実施時にあたって踏襲することが望ましい行動手順や手段のこと。

## Steps(オリジナルの 5 ステップ)
- 1: Collect(収集)
  - 気になることを洗い出す
  - 気になること
    - 頭の中にある「やらなければならないこと」「気になっていること(問題)」
    - 周囲を見て思いついたこと
    - 状況を顧みて思いついたこと
    - 道具や資料を見て思いついたこと
    - その他トリガーリストに頼るのもアリ
  - 洗い出し方
    - 1: まとまった時間を使って集中的に洗い出す
    - 2: 随時洗い出す
  - 洗い出し先は inbox ではない
- 2: Process(処理)
  - 収集した「気になること」をフィルターに入れて各リストに仕分ける
- 3: Organize(整理)
  - 処理した結果をツールに入力する
  - ツールの例
    - タスク管理ツール
    - カレンダー
    - 手帳
    - リストを書き並べたテキストファイル
- 4: Review(見直し)
  - 各リストを現状況に即してメンテナンスする
  - メンテ頻度およびメンテ操作はリスト毎に異なる
  - メンテ頻度
    - 随時
    - 毎日
    - 週一
    - 月一
    - 四半期に一度
    - 年一
  - メンテ操作
    - 項目の追加
    - 項目の編集(変更)
    - 項目の移動
    - 項目の削除
- 5: Do(実行)
  - Nextaction に従って行動する

## Steps(大別した 3 ステップ)
- Input
  - Collect > Process > Organize
  - 頻度は「初回時」と「随時(低頻度)」
- Reflect
  - Review
  - 頻度は「定期的」
- Operate
  - Do
  - 頻度は「毎日」

## Sfuff Filtering
フィルタリング(Filtering)とは「気になること(Stuff)」を仕分けること。意味的判断を要するため自動仕分けは不可能とされている。

### Python コードで擬似的に表すと

```
def filter_stuff(stuff):
  if is_not_actionable(stuff):
    if is_not_need(stuff):
      # Remove the stuff
      return
    if is_document(stuff):
      list_document.push(stuff)
      return
    list_someday.push(stuff)

  if is_not_oneaction_completable(stuff):
    list_project.push(stuff)
    return

  if is_within_2min_completable(stuff):
    # Do the stuff right now
    sleep(120)
    return

  if should_not_act_by_me(stuff):
    list_waiting.push(stuff)
    return

  if has_specific_date(stuff):
    calender.add_event(stuff)
    return

  list_nextaction.push(stuff)
```

### 大雑把に日本語で表すと

```
   気になること
     ||
     VV

1: インボックス

2: いつかやる
   ゴミ箱
   資料フォルダ

3: プロジェクト

4: 2分以内の単一アクション

5: 連絡待ちリスト(誰かからの反応待ち)
   カレンダー(指定日に実行するやつ)
   次に取るべき行動
```

# List
GTD では役割を持ったリストが多数存在する。これらを使いこなすことで GTD を回す。

## 13 List
Height 6 List:

- Nextaction(0m)
- Project(1000m)
- Restriction(2000m)
- Milestone(3000m)
- Ideal(4000m)
- Philosophy(5000m)

Work 5 List:

- Inbox
- Someday
- Calender
- Waiting
- Document

Helper 2 List:

- Context
- Trigger

便宜的に「リスト」と呼称するが実運用上もリストであるとは限らない。たとえばカレンダーはリストではなくカレンダーツールで管理するのが一般的。

## Summary

| List              | List Complexity | List Volume | Review Freq | Filter Step |
| ----------------- | --------------- | ----------- | ----------- | ----------- |
| 5000m Philosophy  | ○ | 1L    | per 360d | -     |
| 4000m Ideal       | ○ | 1L    | per 360d | -     |
| 3000m Milestone   | ○ | 1L    | per 120d | -     |
| 2000m Restriction | ○ | 1L    | A/N      | -     |
| 1000m Project     | △ | 10L   | per 7d   | Step3 |
| 0000m Nextaction  | × | 100L  | Everyday | Step5 |
| Inbox             | ○ | 100L  | -        | Step1 |
| Document          | △ | 100L  | -        | Step2 |
| Someday           | △ | 1000L | -        | Step2 |
| Waiting           | △ | 10L   | -        | Step4 |
| Calender          | △ | 10L   | -        | Step4 |
| Context           | △ | 10L   | -        | -     |
| Trigger           | △ | 10L   | -        | -     |

カラムについて

- Complexity
  - リスト項目の書き方に関する複雑さ
  - ○ は書くだけ、△は要フォーマット工夫、×は要運用工夫・要システム
- List Volume
  - リスト運用時に何行くらいの行を持つか
  - 1, 10, 100, 1000 Line のいずれか
  - 1L は 10 行未満、100L は 1000 行未満
- Review Freq
  - レビュー頻度
- Filter Step
  - フィルタリングのどのステップ中で生成(項目追加)されるか

## Nextaction
Nextaction は「次に取るべき行動」を記したリスト。

| List              | List Complexity | List Volume | Review Freq | Filter Step |
| ----------------- | --------------- | ----------- | ----------- | ----------- |
| 0000m Nextaction  | × | 100L  | Everyday | Step5 |

Nextaction は GTD において最も複雑なリストになる。

Nextaction のボリュームは概ね 1000 行未満である。細かい立場(細かい粒度のタスクを扱うこと)のヘビーなタスク管理ユーザーでもなければ、100 行未満に収まることも珍しくない。細かい立場のヘビーユーザーだと「歯磨き」「ゴミ捨て」「ウェブサイト XXXX の最新記事を見る」といったレベルでルーチンタスクを整えているため、1日のタスク(つまりは次にやること)数は 50 を超え、翌日以降にもびっしりと並ぶため、100 行を超えることが珍しくない。

Nextaction のレビュー頻度は毎日である。実施タイミングは以下の二通り。

- 一日の最初に「今日の」次にやることリストをメンテする
- 一日の終わりに「明日の」次にやることリストをメンテする

Nextaction は 5-Step でいえば Step.5 の Do に相当する。詳しくは後述するが、ユーザーは日々 Nextaction に従うことで日常生活をまわしていく。

### 理想の運用と現実的な運用
ユーザーは常に Nextaction の中から「次にやること」を選ぶのが望ましい。つまり「Nextaction に従っているだけで日常生活がまわる」上体が理想である。もっとも、これを実現することは容易ではなく、単なる TODO リストでは到底実現できない。高級なタスク管理ツールに頼ることになる。

ちなみに他リストのメンテナンスについては、「インボックスを処理する(頻度=4日に1度)(見積:10分)」という「次にやること」を Nextaction に登録しておくことで実現する。無論、この「次にやること」がいつ、どの時間帯に、どれくらいの頻度で登場するようにするかはユーザーが注意深く設定しなければならないし、そもそも「各タスクが適切な頻度でのみ登場する」ことを実現できる機構を備えたタスク管理ツールも習得しなければならない。

つまり理想の運用を実現するためには、以下二つが必要となる。

- 1: Nextaction という「次にやることリスト」を見るだけで生活がまわるよう、Nextaction にどんなタスクを入れればいいかを考え、メンテしていくこと
- 2: 1 を実現するシステムの整備および習熟

これを [ライフプログラミング(LP - Life Programming)](life_programming.md) という。

しかしながら、ライフプログラミングを取り入れることは難しいため、現実的には以下のようになることが多い。

現実的な運用:

- Nextaction は単なる TODO リスト or シンプルなタスク管理ツール
- Nextaction を見る時は、適宜他のリスト(Propject, Calender, Waiting など)も見返す

### 粒度
Nextaction に書く「次にやること」の粒度は、非常に細かいことが望ましい。極論を言えば「今日の自分が見ても、一年後の自分が見ても、何をすればいいかが即座に一意に決まる」レベルである。

例: 新作本の第一章を書く

- そのままと粒度が粗く、Nextaction としては望ましくない
- 粒度を細かくするなら、たとえば次のようになる
  - 新作本の第一章についてブレスト、10分タイマーセットしてキーワードを書き出してみる
  - 新作本の第一章について、5分タイマーとボイスレコーダーをセットしてその場で説明してみる
  - ブログ XXXX から新作本の第一章を書くヒントになりそうな記事タイトルを 15 個コピペして並べてみる
- この細かいものを Nextaction に配置する
- 元々の「新作本の第一章を書く」は Project リストに置くのが望ましい

## Project
...

### 粒度


## Trigger
新たなリスト項目を得るためのヒントを提供するリストをトリガーリストという。一般論で言えば「ひらめきを得るためのヒント集・質問集」。

### 例: 改善するべき不満や問題を洗い出すためのトリガーリスト

```
## 仕事
- 今抱えている PJ
- 今の後に抱えそうな PJ
- 今不満なことは何？
- 今満足していることは何？
- 同部署同僚ー一人一人についてどう思っている？どう思われていそう？
- 上司についてどう思っている？どう思われていそう？
- ステークホルダー一人一人についてどう思っている？どう思われていそう？
- チャット等で絡んでいる一人一人についてどう思っている？どう思われていそう？
- 給与について心配事はある？
- キャリアプランについて心配事はある？

## プライベート
- 今の趣味は何？
- 昔やってた趣味は何？
- やりたいと思っている趣味はある？
- 鍛えたいと思っているスキルはある？
- 衣について不満ややりたいことは？
- 食について不満ややりたいことは？
- 住について不満ややりたいことは？

## 趣味拡充
- 旅行したい場所はありますか？

## 対人関係
- 家族について心配事はある？
- 旧友一人一人についてどう思っている？
- 中高大で友達だった一人一人についてどう思っている？
- 趣味::ダンスラ一人一人についてどう思っている？
- 行きつけの店員さん一人一人についてどう思っている？
- 隣人についてどう思っている？
- 彼女についてどう考えている？
- 結婚についてどう考えている？

## 健康
- 運動の状況は適切ですか？
- 食生活は適切ですか？
- 最近気になっている病気はありませんか？
- ストレスはいつ負荷が大きそうですか？

## お金
- 確定拠出年金はどうなっていますか？適切ですか？
- 加入済の保険はどうなっていますか？適切ですか？
- 加入済の Web サービスはどうなっていますか？適切ですか？
- ここ数ヶ月の収支はプラスですか？マイナスですか？前回と比べてどうですか？

## PC
- 今使っている Windows の不満はなんですか？
- 今使っている MacBookAir の不満はなんですか？
- 今使っているディスプレイの不満はなんですか？
- 今使っている机周りの不満はなんですか？
- 今使っているマウスやキーボードやヘッドホンの不満はなんですか？
- 使ってみたい PC や周辺機器はありますか？
- 今使っているアプリの不満は？
- 形骸化しているディレクトリはありませんか？
- 形骸化している常駐アプリはありませんか？
- 使ってみたいアプリはありますか？

## Web
- 放置しているアカウントはありませんか？
- ブックマークは整理できていますか？
- エゴサーチしてみましたか？ネガティブ意見は書かれてないですか？

## 場所スキャン
場所を思い浮かべて辿ってみることで何かひらめかないか。

- 家
- 会社
- 通勤経路
  - よく行く場所
  - 弁当屋
  - スーパー
  - ゲーセン
  - ……

### 家
- ベランダ
- 居間の床
- 居間の壁
- 居間の窓
- リュック
- 暖房、冷房、扇風機
- 布団、枕
- 机
- 椅子
- 本
- 日用品棚
- 衣服ケース
- クローゼット
- ……

### 会社
- 机の上
- 机の棚
- ロッカー
- ……

### 通勤経路
- 家 to 家最寄り駅
- 家最寄り駅 to 会社最寄り駅
- 会社最寄り駅 to 会社
```

# pGTD - Plaintext GTD
pGTD - Plaintext GTD とはプレインテキストとテキストエディタのみで GTD を実現する仕組みである。

★洗い出す……が、まずはlistセクション埋めた方が良さげ

- 13リスト全部ファイル化する
- nextaction のルーチンタスクを手動でカバーするための策
  - 1: ルーチンタスクをセクション毎にまとめた「ルーチンタスクリスト」。「n日毎に行うタスク」「土曜日に行うタスク」「最終週のどこかでやるタスク」などのセクションがあり、タスクがずらりと並ぶ
  - 2: 今日やるタスクをまとめた「今日リスト」。つまりはデイリータスクリスト
  - 3: 毎日最初に読む「ルーチントリガーリスト」。ここに「今日は～～の日だから～～セクションのタスクを今日リストに追加する」的な指示を書き並べておく。利用者はこれ見るだけで漏れなくルーチン的に処理できる
  - ★でもこれルーチンタスク管理しない派には無用の長物。。。
- テキストエディタ使えないときは「別の手段で記録」「あとで見返して転記」のリマインダーとルーチンタスクを張る

リスト一覧

- 5000m Philosophy
- 4000m Ideal
- 3000m Milestone
- 2000m Restriction
- 1000m Project
- 0000m Nextaction
- Inbox
- Document
- Someday
- Waiting
- Calender
- Context
- Trigger

# Tutorial
★初心者がこれたどれば一通り構築できる……ところを目指したい。まずは雑多に箇条書きして網羅する

Target User

- 人生に対して明確なビジョン、目的、哲学、ミッション等を持っている
- やるべきこと・やりたいことが多すぎて飽和している

Tutorial Flow

- 1: Prepare Workflow
  - Learn about GTD
  - Learn about tools
    - Task management tool
    - Calender/Scheduler
    - Reminder
    - Memo apps
    - Textfile/Texteditor
  - Do collect
  - Do process
  - Select tools or design list format to deal with 13 lists
  - Do organize
  - Add reminder to review in suit timing
- 2: Prepare Height
  - Enumerate Philosophy
  - Enumerate Ideal
  - Enumerate Milestone from Ideal
  - Enumerate Restriction
  - Enumerate Project from Milestone and Restriction
  - Enumerate Nextaction from Project

# Further Reading

## Books
★GTD本読み返して一通り上げてここにも挙げとく

## Net
- [【再掲】GTD歴６年目の私が、これ以上ないくらい丁寧に解説します - BrownDots](https://browndots.net/2015/09/01/gtdmatome/)
  - capture, clarify, organize, reflect, engage という言葉を使っている
- [The GTD Flowchart Explained: Infographic and Process Breakdown](https://flow-e.com/gtd/flowchart/)
