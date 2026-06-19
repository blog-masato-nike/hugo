---
title: "久しぶりの更新"
date: 2022-12-08T21:28:00+09:00
author: Masato Nike
comments: true
tags: ['Octopress', 'Hello World']
---
久しぶりの更新です。<br />
かれこれ2年ぐらい放置していたみたい。<br />
<br />
なぜ放置してたかというと、
メインパソコンをWindows11の高速パソコンに買い替えた際に、
Octopressの環境を入れていなかったため、
環境を構築するの『めんどくさいなぁ』と手つかずでした（汗）<br />
ということで、正直、Octopressの使い方も忘れてしまった（笑）<br />
ということで、正常に投稿できるかわからない（涙）<br />
<br />
さすがに2年間も放置していると、記事を投稿するのに必要なソフトもいろいろ違ってくるようです。<br />
そこで今回は新たにOctopress環境を構築する際に行ったことを書いていきたいと思います。<br />
<!--more-->
<br />
## 1. プログラミング言語『Go』のインストール
<br />
以下のサイトより、最新の『Go』をインストール。<br />
[Downloads - The Go Programming Languag](https://go.dev/dl/ "プログラミング言語『Go』")<br />
<br />
<br />
## 2. 静的Webサイト作成フレームワーク『Hugo』のインストール
Hugo(ヒューゴ）とは、Go言語で書かれた静的 HTML & CSS のWebを作成するフレームワークです。<br />
(1) コマンドプロンプト起動し、以下のコマンドを実行すればインストールできます。<br />
``` bash
go install github.com/gohugoio/hugo@latest
```
<br>
(2) これでHugoがインストールできなので、以下のコマンドで新しいサイト（例 NewSiteName）を作成します。
``` bash
hugo new site NewSiteName
```
<br>
(3) 以下のサイトからHugo Themeをダウンロードしてきます。<br />
[Complete List | Hugo Themes](https://themes.gohugo.io/ "Hugo Themeダウンロードサイト")<br />
※私はいままで使用していたテーマ『bilberry-hugo-theme』を以下のコマンドで、GitHubよりダウンロード（clone）しました。<br />
``` bash
git clone https://github.com/Lednerb/bilberry-hugo-theme.git
```
<br>
(4) 作成したNewSiteNameフォルダ配下の以下のファイルを削除してください。<br />
<br>
NewSiteName/archetypes/default.md<br />
<br>
以下のファイルをNewSiteNameフォルダ配下に上書きコピーします。<br />
<br>
bilberry-hugo-theme/exampleSite/*
<br>
(6) コマンドプロンプトでNewSiteNameに移動してください。<br />
<br>
(7) このテーマだけなのか不明ですが、Hugoモジュールの追加インストールが必要でしたので、以下のコマンドを実施しました。<br />
``` bash
hugo mod init github.com/<your-user>/NewSiteName
```
(8) Hugo Serverが起動するか、以下のコマンドを実施し確認します。
``` bash
hugo server
```
(9) Hugo Serverが正常に起動すれば、以下のサイトにアクセスすればデモサイト（？）が見れるはずです。<br />
<br />
[Hello World! This is the most epic subtitle ever. &vert; My cool new Blog](http://localhost:1313/ "デモサイト")<br />
<br />
## 3. 既存のGitリポジトリのダウンロードとコンテンツのコピー
(1) 以下のコマンドにより、既存のGitリポジトリをダウンロードします。<br />
``` bash
git clone https://github.com/<your-user>/<your-user>.github.io.git
```
<br />
(2) ダウンロードしたリポジトリから以下をコピーします。<br />
<br >
content\post/*<br />

