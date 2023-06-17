---
title: "iPadでVSCodeを使いたいからCodeServerを立てた"
date:
---

iPadでVSCodeを使いたい。でもローカルアプリはリリースされていない。
なので、自宅にあるRaspberry Pi4にCodeServerを立てて、Safariからアクセスすることにした。

```
$sudo apt update
$curl -fsSL https://code-server.dev/install.sh | sh
```
まずCodeServerのインストール。

```
$code-server
```
サーバーの実行。初回起動時にconfigファイルが作成されるので、ここで一旦Ctrl + Cでサーバーを落とす。

```
$nano .config/code-server/config.yaml

bind-addr: 192.168.0.254:8080
auth: password
password: ここにパスフレーズを入れる
cert: false
```
bind-addrを環境に合わせて変更する。

{{< figure src="codeserver.png" title="ブラウザから設定したIPアドレスにアクセスする" >}}

あとはよしなに