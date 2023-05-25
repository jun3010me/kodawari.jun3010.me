---
title: "Hugoのインストール"
date:
---

<a href="https://gohugo.io/" style="text-decoration: none;"><div class="link-box"><div class="img-box"><div style="background-image: url('https://gohugo.io/featured.png');"></div></div><div class="text-box"><p class="title">The world’s fastest framework for building websites</p><p class="description">The world’s fastest framework for building websites</p></div></div></a>

まずはここがHugoの本家のサイト。だけど、ここからはダウンロードしない。実際にファイルを公開しているのはGitHubなので、そっちからダウンロードする。

<a href="https://github.com/gohugoio/hugo/releases" style="text-decoration: none;"><div class="link-box"><div class="img-box"><div style="background-image: url('https://repository-images.githubusercontent.com/11180687/9d3d8200-abf2-11e9-803c-4cdfde0d22e5');"></div></div><div class="text-box"><p class="title">Releases · gohugoio/hugo</p><p class="description">The world’s fastest framework for building websites. - gohugoio/hugo</p></div></div></a>

ここの、hugo_extended_xxxxx_windows-amd64.zipをダウンロードする。

{{< figure src="hugo.png" title="Screenshot" >}}

ダウンロードしたzipを、Cドライブ上に作成したhugoフォルダに展開する。

```
C:\hugo\bin
    hugo.exe
    LICENSE
    README.md
```

ファイルを配置できたら、「C:\hugo\bin」にパスを通しておく。
Windowsでパスを通すやり方は、こちらを参照。

<a href="https://qiita.com/shuhey/items/7ee0d25f14a997c9e285" style="text-decoration: none;"><div class="link-box"><div class="img-box"><div style="background-image: url('https://qiita-user-contents.imgix.net/https%3A%2F%2Fcdn.qiita.com%2Fassets%2Fpublic%2Farticle-ogp-background-9f5428127621718a910c8b63951390ad.png?ixlib=rb-4.0.0&w=1200&mark64=aHR0cHM6Ly9xaWl0YS11c2VyLWNvbnRlbnRzLmltZ2l4Lm5ldC9-dGV4dD9peGxpYj1yYi00LjAuMCZ3PTkxNiZ0eHQ9V2luZG93czEwJUUzJTgxJUE3JUU1JUFFJTlGJUU4JUExJThDJUUzJTgzJTk1JUUzJTgyJUExJUUzJTgyJUE0JUUzJTgzJUFCJUUzJTgxJUI4JUUzJTgxJUFFJUUzJTgzJTkxJUUzJTgyJUI5JUUzJTgyJTkyJUU5JTgwJTlBJUUzJTgxJTk5JUU2JTg5JThCJUU5JUEwJTg2JnR4dC1jb2xvcj0lMjMyMTIxMjEmdHh0LWZvbnQ9SGlyYWdpbm8lMjBTYW5zJTIwVzYmdHh0LXNpemU9NTYmdHh0LWNsaXA9ZWxsaXBzaXMmdHh0LWFsaWduPWxlZnQlMkN0b3Amcz0zOGMwZjE5MzJhMGY4NGU2ODBlMGE2ZTVhZTc2ZTVkYQ&mark-x=142&mark-y=112&blend64=aHR0cHM6Ly9xaWl0YS11c2VyLWNvbnRlbnRzLmltZ2l4Lm5ldC9-dGV4dD9peGxpYj1yYi00LjAuMCZ3PTYxNiZ0eHQ9JTQwc2h1aGV5JnR4dC1jb2xvcj0lMjMyMTIxMjEmdHh0LWZvbnQ9SGlyYWdpbm8lMjBTYW5zJTIwVzYmdHh0LXNpemU9MzYmdHh0LWFsaWduPWxlZnQlMkN0b3Amcz05ODY2YmQwMzIwNmEwNjExZWE0ZDZmYjBiM2JhNWU0OQ&blend-x=142&blend-y=491&blend-mode=normal&s=869971d263b38f57a060d229f10b73ec');"></div></div><div class="text-box"><p class="title">Windows10で実行ファイルへのパスを通す手順 - Qiita</p><p class="description">はじめに パスを通す手順をいつも忘れるのでメモ。そして記憶定着のため。 ステップ1 「システムのプロパティ」ウィンドウを表示させます。 「Windowsキー + s」を押して、表示された検索ボックスに「システムの詳細」...</p></div></div></a>

これをやっておくことで、コマンドプロンプトからhugoコマンドをどこにいても実行できる。

