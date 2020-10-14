---
title: "Web APIの基礎知識"
date: 2020-10-13T17:08:23+09:00
# draft: true
# thumbnail: ".png"
categories:
  - "Development"
tags:
  - "Web API"
  - "API"
  - "github pages"
---
Web APIの基礎知識をググりながら整理する。github pagesでどんなWeb API使えるか、あるいは使えないのか知りたい。

<!--more-->

## Web APIとは

> Web APIとは何なのか  
> 厳格な定義はないが、広義にはHTTPプロトコルを用いてネットワーク越しに呼び出すアプリケーション間、システム間のインターフェースのこと。

AmazonやTwitterがAPIを公開することで収益を拡大してきたらしい。  
具体的にWeb APIはどんな種類のものがあるのか

参考  
[Web APIとは何なのか](https://qiita.com/NagaokaKenichi/items/df4c8455ab527aeacf02)


## Web APIの分類

- クライアントサイド：JavaScript、REST API
    - ブラウザAPI
        > Web ブラウザに組込まれていて、ブラウザやコンピュータの環境の情報を取得し、これを使って役に立つややこしい事を行えるようにするもの
    - サードパーティAPI
        > デフォルトではブラウザに組込まれておらず、普通はコードと情報を Web のどこから読み込まねばなりません。
        - Twitter API, Google Maps API, YouTube API等
- サーバサイド：
    > サーバサイドでHTMLを生成し、生成されたHTMLをクライアントに返却

クライアントサイドならgithub pagesで利用できそう。  
REST APIって何？

参考   
[時代はAPIファースト!? イマドキの業務システム開発ことはじめ 第3回](https://www.knowledgewing.com/kw/blog/2017/03/201703300900.html)  
[Web API の紹介](https://developer.mozilla.org/ja/docs/Learn/JavaScript/Client-side_web_APIs/Introduction)

## REST APIとは
> REST(REpresentational State Transfer)はWebサービスの設計モデルです。RESTなWebサービスは、そのサービスのURIにHTTPメソッドでアクセスすることでデータの送受信を行います。

サンプル（QiitaのREST API）  
> https://qiita.com/api/v2/users/TakahiRoyte
> にアクセスするとJSON(JavaScript Object Notation) というフォーマットのデータを返す

REST APIはgithub pagesで使えるんだろうか？

参考  
- [REST入門 基礎知識](https://qiita.com/TakahiRoyte/items/949f4e88caecb02119aa)

## github pagesでREST APIは使えるか
- github pagesでJavaScriptが動作するWebサイトは公開可能
- JavaScriptからREST APIを呼び出すのもできる
- ただし、ソースが公開されちゃうので、アクセストークンや認証まわりをセキュアにするにはOAuth.io等の工夫が必要

参考
[GitHub Pages 上で Web Application Flow で GitHub API を使用する](https://qiita.com/yuya_takeyama/items/5ee0fe953b0848cd63fb)  
[GitHub PagesでJavascriptが動作するWebサイトを無料公開してみた](https://www.apnari.com/entry/GitHubPages-intro)  
[GitHub Pages を使った静的サイトの公開方法が、とても簡単になっていた](https://www.tam-tam.co.jp/tipsnote/html_css/post11245.html)
