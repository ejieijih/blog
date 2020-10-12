---
title: "Hugoを使ってGithub pages上にブログを作る(Windows)"
date: 2020-10-12T15:13:39+09:00
categories:
  - "Development"
tags:
  - "hugo"
  - "github pages"
  - "Windows"
---

<!--more-->

## 下準備
- Windowsにhugo, gitをインストールしておく
- githubのアカウントとブログ用のリポジトリを作っておく
- Windowsからgithub上のリポジトリにアクセスできるようにsshの設定をしておく
- hugoのテーマを決めておく
- Windows上でブログを置くフォルダを決めておく

## 作業
コマンドプロンプトを管理者権限で立ち上げる

ブログを置くフォルダに移動する
```sh
> cd [ブログを置くフォルダ]
```

powershellでの作業に切り替える
```sh
> powershell
```

サイトの基盤を作る
```sh
> hugo new site blog
```

githubと同期しておく
```sh
> cd blog
> git init
> git pull git@github.com:[github上のブログ用リポジトリ].git
```

テーマをとってくる
```sh
> git submodule add https://github.com/vimux/mainroad themes/mainroad
```

テーマのサンプル設定を反映する
```sh
> cp -Force -Recurse .\themes\mainroad\exampleSite\* .
```

`config.toml`を最低限編集

```toml:config.toml
+ publishDir = "docs"
+ baseurl = "http://[githubアカウント].github.io/[ブログ用リポジトリ名]/"　# "https"はだめ、最後に"/"必須なので注意

- baseurl = "/"
```

hugoでビルドして、githubと同期
```sh
> hugo
> git add -A
> git commit -am "initial commit"
> git push git@github.com:[github上のブログ用リポジトリ].git master
```

github上で、github pages公開の設定をする
- github pages用に作ったリポジトリに行く
- Settings > Options > github pagesに行く
- `Branch: master, /docs`でsaveする

公開されたページに行く
- (http://[githubアカウント].github.io/[ブログ用リポジトリ名]/)

## 参考
[Hugo + GitHub Pages + 無料で洒落たブログを30分で作る](https://qiita.com/yotsak/items/017734d5f873f4f194d4)