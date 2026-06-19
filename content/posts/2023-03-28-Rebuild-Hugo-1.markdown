---
title: "第1回 Hugo環境再構築 ～前提からデモサイト表示まで～"
date: 2023-03-28T11:14:00+09:00
author: Masato Nike
comments: true
tags: ['Hugo']
---
前回の投稿から随分と経過してしまいました…

Hugo環境再構築の第1回になります。  
以下もあわせてお読みいただけると幸いです。  
  
[第1回 Hugo環境再構築 ～前提からデモサイト表示まで～](/posts/2023-03-28-rebuild-hugo-1// "第1回 Hugo環境再構築 ～前提からデモサイト表示まで～")  
[第2回 Hugo環境再構築 ～既存ソース取得からHugo基本設定まで～](/posts/2023-03-28-rebuild-hugo-2/ "第2回 Hugo環境再構築 ～既存ソース取得からHugo基本設定まで～")  
[第3回 Hugo環境再構築 ～一番ハマったHugoのSyntaxHighlight～](/posts/2023-03-28-rebuild-hugo-3/ "第3回 Hugo環境再構築 ～一番ハマったHugoのSyntaxHighlight～")  

<!--more-->
## 0. 2022年12月8日時点の最新のバージョン

|ソフトウェア|バージョン|
|:--|:--:|
|Go|go1.19.4|
|Hugo|v0.108.0|
|bilberry-hugo-theme|2.0.0|

## 1. プログラミング言語『Go』のインストール
  
以下のサイトより、最新の『Go』をインストール。  
[Downloads - The Go Programming Languag](https://go.dev/dl/ "プログラミング言語『Go』")  
  
  
## 2. 静的Webサイト作成フレームワーク『Hugo』のインストール
Hugo(ヒューゴ）とは、Go言語で書かれた静的 HTML & CSS のWebを作成するフレームワークです。  
(1) コマンドプロンプト起動し、以下のコマンドを実行すればインストールできます。  
``` bash
go install github.com/gohugoio/hugo@latest
```

(2) これでHugoがインストールできなので、以下のコマンドで新しいサイト（例 NewSiteName）を作成します。  
``` bash
hugo new site NewSiteName
```

(3) 以下のサイトからHugo Themeをダウンロードしてきます。  
[Complete List | Hugo Themes](https://themes.gohugo.io/ "Hugo Themeダウンロードサイト")  
※私はいままで使用していたテーマ『bilberry-hugo-theme』を以下のコマンドで、GitHubよりダウンロード（clone）しました。  
``` bash
git clone https://github.com/Lednerb/bilberry-hugo-theme.git
```

(4) 作成したNewSiteNameフォルダ配下の以下のファイルを削除してください。  

NewSiteName\\archetypes\\default.md  

以下のファイルをNewSiteNameフォルダ配下に上書きコピーします。  

bilberry-hugo-theme\\exampleSite\\*

(6) コマンドプロンプトでNewSiteNameに移動してください。  

(7) このテーマだけなのか不明ですが、Hugoモジュールの追加インストールが必要でしたので、以下のコマンドを実施しました。  
``` bash
hugo mod init github.com/<your-user>/NewSiteName
```
(8) Hugo Serverが起動するか、以下のコマンドを実施し確認します。
``` Shell
hugo server -t bilberry-hugo-theme -D -w
```
(9) Hugo Serverが正常に起動すれば、以下のサイトにアクセスすればデモサイト（？）が見れるはずです。  
  
[Hello World! This is the most epic subtitle ever. &vert; My cool new Blog](http://localhost:1313/ "デモサイト")  
  
