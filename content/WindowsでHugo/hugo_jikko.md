---
title: "Hugoの実行方法"
date:
---

インストールが終わったら、次は実行する。

## 新規サイト作成
C:\hugoの中で、次のコマンドを実行してみる。

```
hugo new site testsite
```

結果、こうなる。

```
c:\hugo>hugo new site testsite
Congratulations! Your new Hugo site is created in c:\hugo\testsite.

Just a few more steps and you're ready to go:

1. Download a theme into the same-named folder.
   Choose a theme from https://themes.gohugo.io/ or
   create your own with the "hugo new theme <THEMENAME>" command.
2. Perhaps you want to add some content. You can add single files
   with "hugo new <SECTIONNAME>\<FILENAME>.<FORMAT>".
3. Start the built-in live server via "hugo server".

Visit https://gohugo.io/ for quickstart guide and full documentation.
```

フォルダツリーを見るとこんな感じ。

```
c:\hugo>tree testsite
フォルダー パスの一覧
ボリューム シリアル番号は 34F2-A383 です
C:\HUGO\TESTSITE
├─archetypes
├─assets
├─content
├─data
├─layouts
├─public
├─static
└─themes
```

以下の作業は、testsite内で行う。

```
cd testsite
```

## ローカルでWebサーバーとして実行する
HugoはWebサーバーとして実行したり、アップロード用のhtmlを書き出したりできる。

まずはWebサーバとして実行してみる。

```
hugo server -D
```
これで、サーバーとして実行できる。

実行中は、こういう画面が表示される。

```
c:\hugo\testsite>hugo server -D
Start building sites …
hugo v0.111.3-5d4eb5154e1fed125ca8e9b5a0315c4180dab192+extended windows/amd64 BuildDate=2023-03-12T11:40:50Z VendorInfo=gohugoio
WARN 2023/05/20 18:05:16 found no layout file for "HTML" for kind "taxonomy": You should create a template file which matches Hugo Layouts Lookup Rules for this combination.
WARN 2023/05/20 18:05:16 found no layout file for "HTML" for kind "home": You should create a template file which matches Hugo Layouts Lookup Rules for this combination.
WARN 2023/05/20 18:05:16 found no layout file for "HTML" for kind "taxonomy": You should create a template file which matches Hugo Layouts Lookup Rules for this combination.

                   | EN
-------------------+-----
  Pages            |  3
  Paginator pages  |  0
  Non-page files   |  0
  Static files     |  0
  Processed images |  0
  Aliases          |  0
  Sitemaps         |  1
  Cleaned          |  0

Built in 50 ms
Watching for changes in c:\hugo\testsite\{archetypes,assets,content,data,layouts,static}
Watching for config changes in c:\hugo\testsite\config.toml
Environment: "development"
Serving pages from memory
Running in Fast Render Mode. For full rebuilds on change: hugo server --disableFastRender
Web Server is available at http://localhost:1313/ (bind address 127.0.0.1)
Press Ctrl+C to stop
```

Ctrl + Cでプロセスを終了できる。

で、表示のとおり、「http://localhost:1313」にブラウザでアクセスすることで、ページが表示できる。
1313はポート番号。

