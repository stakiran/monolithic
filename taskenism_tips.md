---
layout: default
title: Taskenism TIPS
---

タスケニングをサポートするテクニックや考え方を広く紹介する。

# はじめに

## 読み方
- 大見出しにカテゴリを、中見出しにネタを列挙する
- ルーチンタスクの具体例については以下の様に書くことがある
  - `routine「(ルーチンタスク名) @(頻度)」`

## 注意事項
- タスク管理に関する用語は惜しみなく使うことがある

# カテゴリ > 未分類

## Taskenism の 3C 視点
タスケニングに必要な三つの視点。

- Collect
  - 知る/把握する
  - 今日はどのタスクをやるべきか
  - この日に・この時間に行うべきタスクは何か(予定)
  - この日までに・この時間までに行うべきタスクは何か(締切)
- Control
  - 御す/制御する
  - 今日はどのタスクをどの順番でやるか
  - 今日中にやるタスクはどれか(明日以降に回せるタスクはどれか)
    - n日に1回だけ行えばいいタスクはどれか
    - n日に1回だけ行えばいいタスクをいつ行うか
  - このような制御をどうやって実現するか(どんなツールや運用論を使うか)
- Concretize
  - 崩す/細分化する/具体化する
  - この目標を達成するために必要な行動は何か
  - この目標を達成するために必要な行動はどこまで終えているか

## セクション
「時間帯」の意。

- ルーチンタスクの大半は「いつやるか」がおおよそ決まっているため、セクションを意識してタスケニングすると管理・適応しやすい
- セクションを意識することで、時間帯毎に想定される状況・状態を考慮したタスケニングが行える
  - 例1: 朝は集中できるから創造的なタスクをやる
  - 例2: 午後 13-14 時は眠くなりがちだから作業系のタスクを入れて頭を温める

# カテゴリ > タスクの種類

## インボックス
気になることを入れた何か。

例:

- 郵便受け
- メールの受信ボックス
- 後で処理する書類を溜めてるトレー
- 「あとでやること」リスト
- 頭の中だけにある「気になること」

インボックスは溜まり方と存在形態で分けることができる。ただし脳内だけは例外。

|                            | 溜まり方 | 存在形態 |
| -------------------------- | -------- | -------- |
| 郵便受け                   | 勝手に   | 物理     |
| メールの受信ボックス       | 勝手に   | 電磁     |
| 書類を溜めたトレー         | 自分で   | 物理     |
| あとでやることリスト(紙)   | 自分で   | 物理     |
| あとでやることリスト(PC)   | 自分で   | 電磁     |
| 脳内にある「気になること」 | -        | -        |

運用について:

- 勝手に溜まるインボックス
  - 定期的に処理する
    - 処理とは何らかの行動を伴わせること
  - 生産性の観点では逐次処理よりもバッチ処理(まとめて読んでまとめて処理する)が良い
- 自分で溜めるインボックス
  - 定期的に収集する
    - 集中収集(数十分～数時間をかけてじっくり洗い出す)
    - 瞬間収集(思いついたことを素早く記録する)
  - 収集したものは定期的に処理する

## タイニータスク
2分以内に終了できる、具体的に行動可能なタスク。

- タイニータスクは管理コストよりも実行コストが小さいため、タスケニングせずその場で終わらせてしまうのが望ましい
  - `管理コスト > 実行コスト`
- ただし……
  - タイニータスクの数が多い場合は、把握しきれず忘迷怠になりやすいのでタスケニングする
  - タスケニング手段が非常に効率的な場合は、`実行コスト >> 管理コスト` となっているため、あえて管理しても非効率にはなりにくい
- タイニーの定義と(タスケニングせずに)扱える量は人それぞれ
  - よく有名で有能な者が「タスク管理は不要。その場で終わらせていけばいい」と言うが、それは頭の性能が良くてたとえば「タイニー = 10分以内」「15個くらいは忘迷怠無しでいける」なんてことになっている
  - 凡人は「2分以内」「3個くらいでもう忘迷怠が起きる」レベルもざら(と思う)

# カテゴリ > リスト

## タスクリスト
タスクを記したリスト。

- 単なる箇条書きもあれば、ソフトウェア的に高級な操作やフォーマットを搭載したものもある
- タスクの管理はほぼリストによって実現される
  - リスト以外にあるとすれば [カード方式](task_management.md#カード方式) くらいか

## オープンリスト/クローズドリスト
(特にタスク)リストの性質を表す言葉。

- オープンとはリストを編集できる、の意
- クローズドとはリストを編集できない、の意

リストの中身を作り込む時はオープンにする。リストを利用する時はクローズドにする。つまり編集と利用を混同させないために、オープン・クローズという概念を明示的に取り入れる。

## 予定リスト
予定を列挙したリスト。

- カレンダーを使わずに済ませることができる
  - 例: 「予定リストを毎日見る」「まだ入れてない予定をリストに書く」ルーチンタスクを仕込む
- フォーマットを工夫すれば週報などの提出用にもそのまま使える

例:

```
- 09/30 mon 1230-    XXXX に関する打ち合わせ in YYYY 会議室
- 09/30 mon 1730-    夕礼
- 10/01 mon 0930-    朝礼 in 事業所 AAAA、BBBB 会議室
```

## 連絡待ちリスト
A さんからの連絡待ち、を記したリスト。

- 連絡待ち(相手がアクションを起こさないと先に進まない状態)を忘れることなく対処する簡易的な手段
- そもそも連絡待ちに対してできること
  - 連絡待ちとして何があるかを把握しておく
  - 連絡待ちをこまめにチェックし、鈍いようなら催促を入れる
- 連絡待ちリストの運用
  - 連絡待ちが発生したら、連絡待ちリストに追記する
  - ルーチンタスクで一日一回くらい連絡待ちリストを眺めるようにする
  - 進展があった項目は削除する

例:

```
- 2018/09/26 A事業所からPCパーツ届く
- 2018/10/01 11月休暇申請
```

## ネタリスト
ネタ(創作、発信、その他仕事や趣味などで用いるネタ)を記したリスト。

- ネタをタスクとして扱うとタスクリストが破綻するため、ネタリストを別につくっておくのが賢い
- 無意識的に活用できるようになるまではルーチンタスクで誘導するのもアリ
  - 例: routine「ネタリスト見て今日書くネタ決めよう @1」
  - 例: routine「次の一週間で書くネタを 7 個選んでタスクリストに配置する @毎日曜日」
- メンテナンスは定期的に行う。ネタリストが肥大化すると形骸化しやすい
  - 例: routine「意味不明なネタを削除する @7」
  - 例: routine「もうやった or やめたネタを削除する @14」
  - 例: routine「正直微妙だと思うネタを削除する @14」
- ネタの追加方法も悩ましい
  - 一行一ネタで書く
    - :o: 速い
    - :x: 後で読みづらい
  - 一行一ネタでタグ付で書く
    - :o: まあまあ速い
    - :o: あとで grep すれば絞り込める
    - :x: タグの入力が面倒

# 参考
- [タスク管理](task_management.md)
- [ライフプログラミング](life_programming.md)