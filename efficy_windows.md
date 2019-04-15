---
layout: default
title: Windows PC の効率化
---

# このドキュメントについて
Windows PC の操作を効率化するための概念や手法全般をひたすら簡潔な備忘録で貯める試み。

# 書き方について
- 大見出しはカテゴリ
- 中見出しはネタ単位
- 小見出し以降は使わない

# ウィンドウ
列挙、表示、制御……と観点がまだ見えないのでいっしょくたにする。

## タブインターフェース

## Altab
alt + tab。シンプルな代替 vista switcher。cloc のキーワードマッチングみたいな別代替もある。

## 仮想デスクトップ

## Window Manager
Windows では馴染みないか。Tile Manager とか。表示を完全にシステムに任せるやつ

## Caption Control
タイトル文字列を固定したり色付けしたりして視覚的に見易くする。XFinder はタブレベルだが優秀。秀丸エディタもマクロ使えばできないことはない。teraterm 複数枚使ってた時も自作ツールでこれしてた。

## Taskbar Control
並び替えるフリーソフトとかあった。もう古い。

## Smart Grabbing
窓掴み。mac で言えば bettertouchtool のあれ。

## Holding

# 操作アサイン系

## マウスジェスチャー

## ホットキー

# Security Breaking

## スクリーンセーバーブレイク

## スケジューリング設定変更

## ターゲット変更による特殊フォルダ名変更

# ファイルアクセス

## プログラムランチャ

## ファイラー

## コマンドエイリアス
doskey とか、path 通したコマンド置くとか。

path、pathext もここ？


# 履歴管理

## バージョン管理
git。

## System Recent
最近使ったファイル

## Application Recent
アプリのファイル履歴全般。データはレジストリだったり appdata 配下にファイルとして存在してたり。引き継ぎ時はたいてい死にデータになる。スクリとかでデータ抽出してランチャーに入れてやると便利。

## クリップボード履歴

# 画像系

## キャプチャツール
winshot

## 画像ビューワ
Massigra みたいなやつ。サムネイル image2html もこれか。ファイラーから直接見るタイプ（xfinderやあふｗ）

# レジストリ管理

## regjumpみたいにregedit操作する系

## 俺エディタみたいに独自エディタ

## reg コマンドなど cui

## regedit

# ●misc
・汎用的
 ・単発キー massigra,あふｗ,...
 ・二段 sskeylaucncher,tritask menu
 ・local better than cloud  ブラウザ利用ではなくクライアントソフト利用
 ・why not gui but cui  なぜCUIなのか

・menu accelerator
・process control
・do not tidy, find   everythingとか？
・movie player    windows media player からの脱却？
・ide
・ファイル比較 winmerge
・ブックマーク理論
・パッケージ管理
・圧縮解凍最適化？
・ドキュメントビルド
・エディタ系
・スクリプト系   bat vbs py ahk macro
・自動化とは  コマンド使うこと 仕組みが自動化に対応していること
・表示時間処理時間の削減？


・窓の杜 https://forest.watch.impress.co.jp/library/nav/genre/dktp/ デスクトップ
 ・デスクトップ機能拡張
 ・ウィンドウ機能拡張
 ・ランチャ
 ・アイコンカーソル
 ・クリボ
 ・画面キャプチャ
 ・カレンダー
 ・時計タイマー
 ・付箋メモ
・vector https://www.vector.co.jp/vpack/filearea/win/util/index.html?ref=top ユーティリティ
 ・クリボ
 ・タスク制御
 ・ファイル管理 ファイラ 検索 コピー 削除系
 ・セキュリティ パスワード生成管理 暗号化 起動終了ロギング
 ・システム起動 スタートアップ タイマー終了「
 ・テキストファイル系
 ・デスクトップ系 サイズ位置変更 表示拡大
 ・ランチャ
 ・操作 キーボ系 マウス系
 ・環境設定 窓の手とかそういう系
