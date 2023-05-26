---
title: "Hugo + GitHub Actionの環境をiPadのみで構築する"
date:
---

## GitHubでの準備作業
{{< figure src="IMG_5072.jpeg" title="GitHub Pages用に作るので、Publicで" >}}
まず、リポジトリを作成する。

{{< figure src="IMG_5073.jpeg" title="Settings→Pages→GitHub Actionsを選んで、その中からHugoのConfigureを選択する" >}}
リポジトリが作成できたら、GitHub Actionを設定する。

{{< figure src="IMG_5074.jpeg" title="" >}}
すると中身の確認画面が出るので、そのままCommit Changeする。

## Working Copyでリポジトリの設定をする

iPadでGitHubを使うのにおすすめなアプリが、Working Copyだ。

<div class="cstmreba"><div class="pochireba"><a href="https://apps.apple.com/jp/app/working-copy-git-client/id896694807?uo=4&at=11l7ge"><img src="https://is2-ssl.mzstatic.com/image/thumb/Purple126/v4/99/be/bd/99bebd3d-e89d-6e16-9542-9e3bb87f2bd5/Regular-Icon-0-1x_U007emarketing-0-0-0-7-0-0-85-220.png/60x60bb.jpg" alt="Working Copy - Git client" width="60" height="60" class="pochi_img" ></a><div class="pochi_info"><div class="pochi_name"><a href="https://apps.apple.com/jp/app/working-copy-git-client/id896694807?uo=4&at=11l7ge">Working Copy - Git client</a></div><div class="pochi_price">無料</div><div class="pochi_seller"><a href="https://apps.apple.com/jp/developer/anders-borum/id343532883?uo=4&at=11l7ge">Anders Borum</a></div><div class="pochi_time">(2023.05.26時点)</div><div class="pochi_post">posted with <a href="http://pochireba.com" rel="nofollow" target="_blank">ポチレバ</a></div></div><div class="pochireba-footer"></div></div></div>

{{< figure src="IMG_5076.png" title="リポジトリ登録の様子" >}}
このアプリで、さっき作成したリポジトリを登録することで、iPadの「ファイル」アプリから直接編集ができるようになる。

## iSHでHugoをインストール
別ページにも書いたが、iSHというアプリで使えるシェルが実はx86版Alpine Linuxが仮装で動いているので、これを利用させてもらう。

<div class="cstmreba"><div class="pochireba"><a href="https://apps.apple.com/jp/app/ish-shell/id1436902243?uo=4&at=11l7ge"><img src="https://is3-ssl.mzstatic.com/image/thumb/Purple116/v4/7a/78/e3/7a78e31a-10c7-f56e-822d-c1edf05d66e2/AppIcon-0-0-1x_U007emarketing-0-0-0-7-0-0-sRGB-0-0-0-GLES2_U002c0-512MB-85-220-0-0.png/60x60bb.jpg" alt="iSH Shell" width="60" height="60" class="pochi_img" ></a><div class="pochi_info"><div class="pochi_name"><a href="https://apps.apple.com/jp/app/ish-shell/id1436902243?uo=4&at=11l7ge">iSH Shell</a></div><div class="pochi_price">無料</div><div class="pochi_seller"><a href="https://apps.apple.com/jp/developer/theodore-dubois/id1432356577?uo=4&at=11l7ge">Theodore Dubois</a></div><div class="pochi_time">(2023.05.24時点)</div><div class="pochi_post">posted with <a href="http://pochireba.com" rel="nofollow" target="_blank">ポチレバ</a></div></div><div class="pochireba-footer"></div></div></div>

```
apk add hugo
```

ただし、iSH上でHugo Serverを実行してもサーバーアプリとして機能してくれない。なので、新規でサイトを作成するだけにして、実際に動かすのをGitHub Pages上でやりましょうという計画のつもり。

```
hugo new site hugo
```
これで、新規サイト用のファイルがhugoディレクトリに展開される。

あとはお好みで、themesディレクトリ上に使いたいテーマを入れておく。

なお、ほとんどのテーマはgitで取得できるので、gitコマンドを取得しておくことをおすすめする。

```
apk add git
```
あとは用意できたファイル群をGitHubで作ったリポジトリに放り込んで、コミットするだけだ。