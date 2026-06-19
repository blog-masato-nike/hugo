---
title: "第3回 Hugo環境再構築 ～一番ハマったHugoのSyntaxHighlight～"
date: 2023-03-28T11:18:00+09:00
author: Masato Nike
comments: true
tags: ['Hugo', 'Syntax', 'Highlight', 'SyntaxHighlight']
---
Hugo環境再構築の第3回になります。  
2022年12月8日現在のHugo環境ではここが一番ハマりました。  
なんとか見てくれは成功しましたが、個人的には納得がいかず、時間があるときに再調査したいぐらいです。  

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

## 4. HugoのSyntaxHighlight

Hugo公式サイトのSyntax Highlightの説明をみると、Go言語でビルドされたChromaのシンタックスハイライトが用意されているらしい。  

[Syntax Highlighting | Hugo](https://gohugo.io/content-management/syntax-highlighting/ "Hugo公式 | Syntax Highlighting")


(1) 以下のコマンドし、"monokai"のスタイルシートを生成します。  
``` Shell
hugo gen chromastyles --style monokai > syntax.css
```
(2) 生成したsyntax.cssを以下のフォルダにします。  

content\static\css  

(3) 設定ファイル『config.toml』に[markup.highlight]セクションを新規に追加します。


|項目|値|備考|
|:--|:--:|:--|
|anchorLineNos|||
|codeFences|true|markdownのコードブロックをsyntaxhighlightする|
|guessSyntax|false||
|hl_Lines|''||
|hl_inline|false||
|lineAnchors|''||
|lineNoStart|1||
|lineNos|false||
|lineNumbersInTable|true||
|noClasses|false||
|noHl|false||
|style|'monokai'||
|tabWidth|4||

