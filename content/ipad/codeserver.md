---
title: "iPadでVSCodeを使いたいからRaspberry Pi 4でCodeServerを立てた"
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

```
$sudo mv /lib/systemd/system/code-server@.service /lib/systemd/system/code-server.service
```
code-server.serviceのファイル名に@がついていたので、mvコマンドで@を取ってから

```
$sudo nano /lib/systemd/system/code-server.service
```
ファイル名を変更したcode-server.serviceをエディタで以下の通りに編集する。

```
[Unit]
Description=code-server
After=network.target

[Service]
Type=exec
ExecStart=/usr/bin/code-server
Restart=always
User=ここにユーザー名を入れる

[Install]
WantedBy=default.target
```
って言っても、ユーザー名を入れるだけ。

```
$sudo systemctl enable code-server
$sudo systemctl start code-server
```
これでサービスとして有効になったし、起動もした。

あとはよしなに。