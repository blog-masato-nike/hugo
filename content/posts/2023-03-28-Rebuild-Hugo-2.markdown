---
title: "第2回 Hugo環境再構築 ～既存ソース取得からHugo基本設定まで～"
date: 2023-03-28T11:17:00+09:00
author: Masato Nike
comments: true
tags: ['Hugo']
---
Hugo環境再構築の第2回になります。  
以下もあわせてお読みいただけると幸いです。  
  
[第1回 Hugo環境再構築 ～前提からデモサイト表示まで～](/posts/2023-03-28-rebuild-hugo-1// "第1回 Hugo環境再構築 ～前提からデモサイト表示まで～")  
[第2回 Hugo環境再構築 ～既存ソース取得からHugo基本設定まで～](/posts/2023-03-28-rebuild-hugo-2/ "第2回 Hugo環境再構築 ～既存ソース取得からHugo基本設定まで～")  
[第3回 Hugo環境再構築 ～一番ハマったHugoのSyntaxHighlight～](/posts/2023-03-28-rebuild-hugo-3/ "第3回 Hugo環境再構築 ～一番ハマったHugoのSyntaxHighlight～")  

<!--more-->
  
## 3. 既存のGitリポジトリのダウンロードとコンテンツのコピー
(1) 以下のコマンドにより、既存のGitリポジトリをダウンロードします。  
``` Shell
git clone https://github.com/<your-user>/<your-user>.github.io.git
```
  
(2) ダウンロードしたリポジトリから以下をコピーします。  

content\\post\\*  
content\\static\\*  
layouts\\partials\\*  
static\\css\\*

(3) あとはそれぞれの既存リポジトリから取得した環境に応じて、「ico」とか「images」とかもコピーしてください。  

(4) 私の場合は過去の記事の中でscriptタグを利用していたので、別途2つのファイルを作る必要がありました。  

layouts\\shortcodes\\script.html
```JavaScript
<script>
{{ .Inner | safeJS }}
</script>
```
layouts\\shortcodes\\rawhtml.html
```Shell
{{ .Inner }}
```


(5) 設定ファイル『config.toml』を既存環境に合わせ以下の編集します。  

トップセクション
|項目|値|備考|
|:--|:--:|:--|
|title|||
|baseURL|||
|theme|"bilberry-hugo-theme"||
|DefaultContentLanguage|"ja"||
|googleAnalytics|||
|disqusShortname|||
|author|||
|description|||
|keywords|||
|subtitle|||
|avatarEmail|||
|customImage|||
|overlayIcon|||
|dateFormat|"2006-01-02 15:04:05"||
|copyrightBy|"by Masato Nike"||
|copyrightUseCurrentYear|false||
|copyrightYearOverride|"2016-2022"||
|creditsText|"Bilberry Hugo Theme"||
|pygmentsUseClasses|true|style属性ではなくclass属性でスタイルを指定|
|pygmentsCodeFences|true|markdownのコードブロックをsyntaxhighlightする|
|customCSS|||

[[params.links]]セクション
|項目|値|備考|
|:--|:--:|:--|
|title|"Link"||
|href|"/"||

[Languages]はすべてコメントアウトしました。
