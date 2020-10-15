---
title: "Web APIとそのgithub pagesでの利用"
date: 2020-10-13T17:08:23+09:00
draft: true
# thumbnail: ".png"
categories:
  - "Development"
tags:
  - "Web API"
  - "API"
  - "github pages"
---
Web APIとはどういうもので、github pagesで使えるのか調べる。Web APIとはhttp経由で呼び出せるアプリで、特にサーバサイドで使えるREST APIは、githubでも使えるらしい。

<!--more-->

## Web APIとは

> Web APIとは何なのか  
> 厳格な定義はないが、広義にはHTTPプロトコルを用いてネットワーク越しに呼び出すアプリケーション間、システム間のインターフェースのこと。

引用: [Web APIとは何なのか](https://qiita.com/NagaokaKenichi/items/df4c8455ab527aeacf02)

AmazonやTwitterはAPIを公開することで収益を拡大してきたらしい  
Web APIにはどんな種類のものがある？

## Web APIの分類

クライアントサイドAPI：JavaScript、REST API
- ブラウザAPI
    > Web ブラウザに組込まれていて、ブラウザやコンピュータの環境の情報を取得し、これを使って役に立つややこしい事を行えるようにするもの
- サードパーティAPI
    > デフォルトではブラウザに組込まれておらず、普通はコードと情報を Web のどこから読み込まねばなりません。
    - Twitter API, Google Maps API, YouTube API等

引用: [Web API の紹介](https://developer.mozilla.org/ja/docs/Learn/JavaScript/Client-side_web_APIs/Introduction)

サーバサイド：
> サーバサイドでHTMLを生成し、生成されたHTMLをクライアントに返却

引用: [時代はAPIファースト!? イマドキの業務システム開発ことはじめ 第3回](https://www.knowledgewing.com/kw/blog/2017/03/201703300900.html)  

クライアントサイドならgithub pagesで使えるだろうか  
流行りのREST APIってどんなもの？

## REST APIとは
> REST(REpresentational State Transfer)はWebサービスの設計モデルです。RESTなWebサービスは、そのサービスのURIにHTTPメソッドでアクセスすることでデータの送受信を行います。

引用: [REST入門 基礎知識](https://qiita.com/TakahiRoyte/items/949f4e88caecb02119aa)

REST APIのサンプル（QiitaのREST API）  
```
https://qiita.com/api/v2/users/TakahiRoyte
にアクセスするとJSON(JavaScript Object Notation) というフォーマットのデータを返す
```
参考: [REST入門 基礎知識](https://qiita.com/TakahiRoyte/items/949f4e88caecb02119aa)

REST APIの構造を知るにはここ  
[0からREST APIについて調べてみた](https://qiita.com/masato44gm/items/dffb8281536ad321fb08)

REST APIはgithub pagesで使える？

## github pagesでREST APIは使えるか
- github pagesでJavaScriptが動作するWebサイトは公開可能
- JavaScriptからREST APIを呼び出すのもできる
- ただし、ソースが公開されちゃうので、アクセストークンや認証まわりをセキュアにするにはOAuth.io等の工夫が必要

参考  
[GitHub Pages 上で Web Application Flow で GitHub API を使用する](https://qiita.com/yuya_takeyama/items/5ee0fe953b0848cd63fb)  
[GitHub PagesでJavascriptが動作するWebサイトを無料公開してみた](https://www.apnari.com/entry/GitHubPages-intro)  
[GitHub Pages を使った静的サイトの公開方法が、とても簡単になっていた](https://www.tam-tam.co.jp/tipsnote/html_css/post11245.html)

実際にgithub上のwebサイトでJavaScriptを動作させてREST APIを呼び出してみたくなった  
JavaScriptを勉強しながらやってみたい

## まとめ
- Web APIとはどういうもので、github pagesで使えるのか調べた
- Web APIとはhttp経由で呼び出せるアプリで
- 特にサーバサイドで使えるREST APIは、githubでも使えるらしい
- 実際にやってみたい