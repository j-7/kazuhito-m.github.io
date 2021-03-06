---
layout: post
title:  勉強会行ってみた「おいしがLinux勉強会 Linux Kernel2.6解読室」
category: study-meeting-repo
tags: [linux,kernel,reading]
---

書くといったからには書くのだよ！！

…また、本読めてない状態で行ったし、gdgdだったけど(トホホ

# 情報

- [申し込みサイト](http://oishiga.connpass.com/event/10659/)
- 何するのか
  - 参加前に、予め「決められた本の範囲」を読み
  - GithubのWikiに疑問点書き
  - 当日は読み進めつつ疑問を議論しつつ範囲消化
    - …なのだが「相当かっ飛ばして」進むのでよほど読んでないとついてけないｗ
- 範囲
  - 第１、２、３、４、５、６、７、８章

# なんで来たん？

俺は、Linuxは大好きで、ずっと「ユーザーとして使い続けて」いる。

しかし、内部には全く踏み込まず、読んでも日経Linux程度…。

今回、この勉強会が [@tokutaka](https://twitter.com/tokutaka)
さんにより開かれたのを契機に「カーネルとかもう少し内部に踏み込んでみよう」と考え、参加しました。

# 内容

## 序盤

本日は年始の週末だからか、キャンセル・遅参が多くあるようでした。

そんな中、最初に来てたメンバーで…

- プロ・スキャンスナッパーが教える「高品質(文字列検索可能)ドキュメント」自炊入門
- 20テラ以上！ 高信頼自宅ストレージの構築と運用体験記
- 人柱NexasにUbuntu Touch入れてみた（そしてカーネルパニクった）日記

というテーマでの講義を受けたので、俺にとっては「本編より値千金だった」というのはご愛嬌ｗ

## 開始後

4人来たので「読んだトコで気になったトコ」を流しながら、ディスカッションをしました。

自分は「１章すらまともに読めてない」ので、聞き専に徹してメモをとってました。それがこちら↓

- この本は「カーネルを読むための手引」な感じかも？
- 15章くらいは面白そう
- ubuntu.so がBSD上で動く話
- プロセススケジューラとキューの話が面白い
- わりと「想像可能」なシンプルな実装になっているな
- NMI割り込みであってもマスク出来る(物理)の話
- 実際参加者がみんなLinux端末を持ってる(一部BSD)だから実践出来ておもろい
- Dockerから見える/proc/interupts は外と同じだった
- 「時計」って言う概念は面白くタメになるかも
- 5.3あたりが「セキュアな設計」の時に重要なとこですよね
- システムコールを少ない手順でトレースまでもってけるのはLinuxの良いとこだなあ
- 排他はいろんな概念を考案されたあとが伺えるな
- スピンロックとシーケンスカウンタロックとRCUを上手く使って排他を実現している
- 「出来る限りのシンプルなアルゴリズム、シンプルな名詞で書いたC」は、例えgotoあれどもコメント要らずなくらい読めるものなのかもしれない
- ミウラの「Ubuntu14.10 on
    MBA」だけが「マスク不可割り込みNMIが800超え」とかｗｗ

…ちょっと自分用すぎましたね。

# 感じたこと

- ソース読みも本文中では「わかる程度でそんなに深く切り込んでなく、良い所をチョイスしてる」ので、Cもアルゴリズムも読めない俺でも、時間をかければ読めるのではないか
- 『タスクスケジューラのアイドルプロセス』『ブロックデバイス』『/proc』もそうだが、Linuxの哲学は「出来るだけ統一な土俵を作り、その枠組みになんでも”特別扱いせずよく似た形で”載せてる」ことが、シンプルかつメンテナンスフルに保てている理由なのではないだろうか

# 反省

「俺でも読めるかもしれない」という可能性を見たのに、「読んできていない」のは言語道断だなと。

# 次に向けて

次回は「今回分も含めて」ゆっくり計算して読んでいこう。

---
しっかし…懇親会の「秋吉」の焼き鳥が美味すぎて…終電逃しかけましたｗ
