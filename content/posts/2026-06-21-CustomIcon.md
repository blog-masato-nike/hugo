---
title: "Font Awesomeを使用したカスタムアイコン（X-Twitter）"
date: 2026-06-21T16:26:00+09:00
author: Masato Nike
comments: true
tags: ['Hugo', 'Font Awesome']
featured_image: '/ico/favicon-96x96.svg'
---
私が利用しているHugoのテンプレートにはあらかじめTwitterなどのアイコンがCSSに定義されていましたが、“X”のアイコンがCSSにはありませんでした。
そこで、Font Awesomeのフリーアイコンを使用し、“X”のアイコンを表示する方法を記したいと思います。

<!--more-->

(1) Hugoに以下のようにCSSファイルを格納します。
``` bash
(Hugoホーム)/contents/css/custom.css
``` 
(2) [Font Awesome](https://fontawesome.com/ "Font Awesome")より、表示したいアイコンを探し、SVGの文字列をコピーしてください。

![Font Awesome](/images/blog/2026/06/21/FontAwesome.jpg)
``` bash
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 640 640"><!--!Font Awesome Free v7.2.0 by @fontawesome - https://fontawesome.com License - https://fontawesome.com/license/free Copyright 2026 Fonticons, Inc.--><path d="M453.2 112L523.8 112L369.6 288.2L551 528L409 528L297.7 382.6L170.5 528L99.8 528L264.7 339.5L90.8 112L236.4 112L336.9 244.9L453.2 112zM428.4 485.8L467.5 485.8L215.1 152L173.1 152L428.4 485.8z"/></svg>
``` 

(3) [URL-encoder for SVG](https://yoksel.github.io/url-encoder/ "URL-encoder for SVG")というサイトで、CSS向けにSVGを変換してくれるので、(2)でコピーした文字列を貼り付け、貼り付けた文字列からコメントアウトされている箇所を削除し、URLエンコードしてください。

![URL-encoder for SVG](/images/blog/2026/06/21/URL-encoderforSVG.jpg)

(4) (1)で作成したファイルに以下のように記述してください。（以下は“Twitter X”の例）
``` bash
.fab-x-twitter:before{
    content: '';
    display: inline-block;
    width: 1em;
    height: 1em;
    background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 640 640'%3E%3Cpath d='M453.2 112L523.8 112L369.6 288.2L551 528L409 528L297.7 382.6L170.5 528L99.8 528L264.7 339.5L90.8 112L236.4 112L336.9 244.9L453.2 112zM428.4 485.8L467.5 485.8L215.1 152L173.1 152L428.4 485.8z'/%3E%3C/svg%3E");
    background-repeat: no-repeat;
    background-size: contain;
    background-position: center;
}

``` 
※先頭の『fab』は"Font Awesome Brand"を表しています。

(5) あとは実際に利用するソースで、(4)で作成したクラスを読み込めばFont Awesomeで選んだ画像が表示されます。
