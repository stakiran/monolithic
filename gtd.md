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
...

## Project
...


## Trigger
新たなリスト項目を得るためのヒントを提供するリストをトリガーリストという。一般論で言えば「ひらめきを得るためのヒント集・質問集」。

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
