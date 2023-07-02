---
title: "Windows11の右クリックメニューを従来の表示に戻す"
date:
---

Windows11の右クリックで出てくる簡易メニューが苦手です。
そのアイコンにないことを右クリックからやりたいんじゃ。

そういう人向けのカスタマイズ方法です。

やり方は簡単。コマンドプロンプトを管理者権限で開いて、このコマンドを実行して再起動するだけ。

```
reg.exe add "HKCU\Software\Classes\CLSID\{86ca1aa0-34aa-4e8b-a509-50c905bae2a2}\InprocServer32" /f /ve
```