---
title: "必要なソフトのダウンロードとインストールの方法"
date:
---

## 大前提としての知識
Proxmark3を使うためには、コマンドを扱う知識が必要となる。
探せばGUIツールも出てくるが、バージョンが低いまま開発が止まっていて、全ての機能を扱うことはできない。

なのでProxmark3の全ての機能を使うためには、マウスで操作するのではなく、キーボードでコマンドを入力して操作する方法に慣れる必要がある。

## ビルド済みツールを使う
本来なら、GitHubに公開されているソースコードを自分でコンパイルする必要があるが、ここではそれを省くために、予めWindows向けにビルドされているものを有難くダウンロードすることにする。

<a href="https://www.proxmarkbuilds.org/" style="text-decoration: none;"><div class="link-box"><div class="img-box"><div style="background-image: url('');"></div></div><div class="text-box"><p class="title">Proxmarkbuilds.org</p><p class="description"></p></div></div></a>
{{< figure src="download.png" title="Screenshot" >}}

使う機種に合わせてダウンロードするプログラムを選択する。今回はProxmark3 Easyの利用が目的なので、機種名が入ったリンク先よりビルド済みのファイルをダウンロードする。

ダウンロードしたファイルは拡張子が7z、いわゆる7zipファイルなので、7zipをインストールする必要がある。

[圧縮・解凍ソフト 7-Zip](https://7-zip.opensource.jp/)

{{< figure src="folder.png" title="Screenshot" >}}

圧縮ファイルを解凍すると、こちらのファイル群が出てくる。基本的に使うのはpm3.batやpm3-flash-all.batなどのバッチファイルだ。

{{< figure src="bat.png" title="Screenshot" >}}

これがバッチファイルの中身。修正すべき部分は、Proxmark3がパソコンに認識されているシリアルポートの番号。COM3やCOM4など、環境に合わせて変更する。自分の場合はCOM4だった。この番号が合わないとアプリが起動しない。

それと、「-p」というオプションの引数は必須。これがflash-allなどのバッチファイルでは省略されて書いてあるもんだから不要だと勘違いするかもしれないが、どのバッチにも必要だ。