---
layout: default
title: GTD
---

# Height

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
- 0000m Nextactions
  - デイリータスクリスト
  - カレンダー
  - リマインダー

# Workflow

## Steps
大別した 3 ステップ

- Input
  - Collect > Process > Organize
  - 頻度は「初回時」と「随時(低頻度)」
- Reflect
  - Review
  - 頻度は「定期的」
- Operate
  - Do
  - 頻度は「毎日」

オリジナルの 5 ステップ

- Collect(収集)
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
- Process(処理)
  - 収集した「気になること」をフィルターに入れて各リストに仕分ける
- Organize(整理)
  - 処理した結果をツールに入力する
  - ツールの例
    - タスク管理ツール
    - カレンダー
    - 手帳
    - リストを書き並べたテキストファイル
- Review(見直し) ★これ合ってる？調べると Plan って単語当たってるんだけど……？
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
- Do(実行)
  - Nextaction に従って行動する

## Stuff Filter
気になることを仕分けるためのフィルター。意味的判断を要するため自動化は不可能。

### Algorithm with pythonic

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

### Algorithm with 5 level rough JP

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

## 13 List
- Nextaction(0m)
- Project(1000m)
- Restriction(2000m)
- Milestone(3000m)
- Ideal(4000m)
- Philosophy(5000m)
- Inbox
- Someday
- Calender
- Waiting
- Document
- Context
- Trigger

便宜的に「リスト」と呼称するが実運用上もリストであるとは限らない。たとえばカレンダーはリストではなくカレンダーツールで管理するのが一般的。

★詳細議論に入る前に表でまとめたい

## Summary

| リスト名 | レビュー頻度 | 行数ボリューム | フィルターステップ | 直接記入可？ | リストの複雑さ | 
| --- | --- | --- | --- | --- | --- |
| Inbox | - | 100 | 1 | y | ◎ |

## Nextaction
...

## Project
...


## Trigger
新たなリスト項目を得るためのヒントを提供するリストをトリガーリストという。一般論で言えば「ひらめきを得るためのヒント集・質問集」。

# Tutorial
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
- [【再掲】GTD歴６年目の私が、これ以上ないくらい丁寧に解説します | BrownDots](https://browndots.net/2015/09/01/gtdmatome/)
  - capture, clarify, organize, reflect, engage という言葉を使っている
- [The GTD Flowchart Explained: Infographic and Process Breakdown](https://flow-e.com/gtd/flowchart/)
