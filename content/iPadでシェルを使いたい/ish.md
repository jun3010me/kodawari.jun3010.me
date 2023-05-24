---
title: "ishが面白い"
date:
---

ishというアプリがAppStoreで公開されている。

<div class="cstmreba"><div class="pochireba"><a href="https://apps.apple.com/jp/app/ish-shell/id1436902243?uo=4&at=11l7ge"><img src="https://is3-ssl.mzstatic.com/image/thumb/Purple116/v4/7a/78/e3/7a78e31a-10c7-f56e-822d-c1edf05d66e2/AppIcon-0-0-1x_U007emarketing-0-0-0-7-0-0-sRGB-0-0-0-GLES2_U002c0-512MB-85-220-0-0.png/60x60bb.jpg" alt="iSH Shell" width="60" height="60" class="pochi_img" ></a><div class="pochi_info"><div class="pochi_name"><a href="https://apps.apple.com/jp/app/ish-shell/id1436902243?uo=4&at=11l7ge">iSH Shell</a></div><div class="pochi_price">無料</div><div class="pochi_seller"><a href="https://apps.apple.com/jp/developer/theodore-dubois/id1432356577?uo=4&at=11l7ge">Theodore Dubois</a></div><div class="pochi_time">(2023.05.24時点)</div><div class="pochi_post">posted with <a href="http://pochireba.com" rel="nofollow" target="_blank">ポチレバ</a></div></div><div class="pochireba-footer"></div></div></div>

これがなかなか面白い。
Alpine Linux x86版がどうやら動いているっぽい。

## Alpine Linuxで使うパッケージコマンド「apk」
apkと聞くとAndroidのアプリパッケージの拡張子と同じだけど、Alpine Linuxではこの名前のパッケージ管理システムを使う。Ubuntuでいうところのaptやapt-getに相当する。

アップデートとアップグレード
```
apk update
apk upgrade
```

パッケージの追加
```
apk add パッケージ名
```

検索
```
apk search パッケージ名
```

削除
```
apk del パッケージ名
```

### Hugoがインストールできる
```
apk add hugo
```
これでHugoがインストールできる。ただし、バージョンが古くて、実行できない。

なので、apkで参照するリポジトリを最新のものにする。

```
echo "https://dl-cdn.alpinelinux.org/alpine/v3.18/community/" >> /etc/apk/repositories
echo "https://dl-cdn.alpinelinux.org/alpine/v3.18/main/" >> /etc/apk/repositories
```

「/etc/apk/repositories」がリポジトリのリストが記述されているファイル名。
ここに、Alpine Linuxの最新バージョンである3.18用のmainとcommunityのURLを記述することで、apkコマンドから参照してくれるようになる。echoで追記しているけど、既存のリストを削除しなくても、新しいバージョンのパッケージを取得してくれるのでこのままで良さそう。

ただし、アプリを再起動するとこのリポジトリファイルが元に戻ってしまうので、自分の場合は「repo.sh」にこのecho文を入れて、起動時に手動で実行している。どこかで自動化したいけど、今のところはこれでよし。

```
hugo new site サイト名
```
Hugoで新規サイトを作成する際はこんなコマンドを打つんだけど、ish上で実行すると、高い確率でエラーを吐く。

```
atal: morestack on g0
fatal: morestack on g0
fatal error: unexpected signal during runtime execution
```
こんな感じの。runtime系の長めのエラーが出る時もある。
もうこうなったらどうしようもない。
なぜかCtrl+Cでプロセスから抜けられない。

エラーが出たとしてもプロンプトに帰ってこられるのなら、再度実行するとうまくいくこともあるし、うまくいった後に再度実行してエラーが出る場合もあるから、正常に実行できるかどうかは運任せなところがある。

もしエラーで固まってしまったら、アプリを一旦閉じてから起動し直すしか方法はない。しかも起動し直すとリポジトリは元通りになっているので注意が必要。

