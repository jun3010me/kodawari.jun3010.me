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

で、表示のとおり、「http://localhost:1313」にブラウザでアクセスすることで、ページが表示できる。1313はポート番号。

{{< figure src="image1.png" title="Not Foundと出たら成功" >}}

## Themeを導入する
<a href="https://themes.gohugo.io/" style="text-decoration: none;"><div class="link-box"><div class="img-box"><div style="background-image: url('https://themes.gohugo.io/opengraph/gohugoio-card-base-1_huf001e7df4fd9c00c4355abac7d4ca455_242906_filter_16193305268219998852.png');"></div></div><div class="text-box"><p class="title">Complete List</p><p class="description"></p></div></div></a>

Hugoの本家サイトから良さげなテーマを探す。

今回は、Avaというテーマにしてみる。

<a href="https://themes.gohugo.io/themes/hugo-theme-ava/" style="text-decoration: none;"><div class="link-box"><div class="img-box"><div style="background-image: url('https://themes.gohugo.io/themes/hugo-theme-ava/tn-featured.png');"></div></div><div class="text-box"><p class="title">Ava</p><p class="description">Hugo Ava Theme See online demo Code source demo Installation Install Hugo Follow the official installation guide You need the extended version Create a new Hugo site hugo new site my-site This will create a fresh Hugo site in the folder my-site. Install theme with Git Clone this repo into the themes folder cd my-site git clone https://github.com/jmau111/hugo-theme-ava.git themes/hugo-theme-ava Copy example content You can use contents generated for the demo:</p></div></div></a>

インストール方法は、GitHubに書いてある通り、サイトのフォルダ内でgit cloneする。

```
git clone https://github.com/jmau111/hugo-theme-ava.git themes/hugo-theme-ava
```

そして、ReadMeの通りだと、サンプルファイルをコピーすることになっている。これをやると、とりあえずサイトを表示させることができる。

```
cp -a themes/hugo-theme-ava/exampleSite/. .
```

これはWindowsのコマンドプロンプトでは実行できない、Linux向けのコマンドなので、代わりにこっちを実行する。

```
xcopy /S /E themes\hugo-theme-ava\exampleSite\* .
```

```
c:\hugo\testsite>xcopy /S /E themes\hugo-theme-ava\exampleSite\* .
C:\hugo\testsite\config.toml を上書きしますか (Yes/No/All)? A
themes\hugo-theme-ava\exampleSite\config.toml
themes\hugo-theme-ava\exampleSite\archetypes\default.md
themes\hugo-theme-ava\exampleSite\content\about.md
themes\hugo-theme-ava\exampleSite\content\contact.md
themes\hugo-theme-ava\exampleSite\content\_index.md
themes\hugo-theme-ava\exampleSite\content\posts\example.md
themes\hugo-theme-ava\exampleSite\content\posts\example2.md
themes\hugo-theme-ava\exampleSite\content\posts\example3.md
themes\hugo-theme-ava\exampleSite\content\posts\example4.md
themes\hugo-theme-ava\exampleSite\content\posts\example5.md
themes\hugo-theme-ava\exampleSite\content\posts\example6.md
themes\hugo-theme-ava\exampleSite\content\posts\example7.md
themes\hugo-theme-ava\exampleSite\content\posts\_index.md
themes\hugo-theme-ava\exampleSite\content\posts\example8\index.md
themes\hugo-theme-ava\exampleSite\content\posts\example8\images\shinjuku.jpg
themes\hugo-theme-ava\exampleSite\data\social.json
themes\hugo-theme-ava\exampleSite\data\welcome.json
17 個のファイルをコピーしました
```

上書きするか確認してくるので、「A」で返事する。これで上書き完了。


{{< figure src="image2.png" title="テーマの導入成功" >}}

これで再びサイトを見てみると、自動で更新されている。もしテーマの導入の過程で一度サーバーを終了したなら、再度実行することで確認できる。
