---
title: "hugoでサムネ画像をtwitter cardに反映"
date: 2020-10-13T14:29:03+09:00
# draft: true
thumbnail: "twitter_card.png"
categories:
  - "Development"
tags:
  - "hugo"
---
hugoのtheme: mainroadはtwitter card自体には対応しているけど、画像は反映されないので、反映されるように改造する
<!--more-->

### 記事のサムネ画像を設定

画像を`static/`に画像(ここではtest.png)を置く
```sh
static/test.png
```

記事（～.md）のfront-matter（冒頭部分）にサムネイル情報を追記
```sh:test.md
---

+ thumbnail: "test.png"

---
```

### twitter cardの画像をサムネ画像に設定

`themes/mainroad/layouts/_default/baseof.html`をエディタで開いて、headの中に以下のメタタグを追記
```html
<meta name="og:image" content="{{ .Site.BaseURL }}{{ .Params.thumbnail }}" />
```

ビルドして反映
```sh
> hugo
```

反映されているか確認

`docs/post/[記事名]/index.html`に以下が反映されていればok
```html
<meta name="og:image" content="[サイトのurl]/test.png" />
```

github pagesと同期
```sh
git add -A
git commit -am "add twitter-card image"
git push remote
```

[twitter card validator](https://cards-dev.twitter.com/validator)で動作確認

![twitter_card](../../twitter_card.png)

# 参考
- [HugoでのTwitterカード設定サンプル](https://qiita.com/alkn203/items/5f781d5d6ad6e400d812)
- [twitter card validator](https://cards-dev.twitter.com/validator)