---
title: arch linux 復旧法
author: naniwa
type: post
date: 2014-10-27T17:47:21+00:00
excerpt: |
  |
url: /wordpress/122/
categories:
  - 未分類

---
さっきサーバーをリブートしたら立ち上がらず、心当たりといえば、usbメモリを無断で抜いたことなんだが（おい。。。
  
エラーを見る限り、カーネルが壊れた模様。

archのインストールusbを作成してarch-chrootコマンドでrootを乗っ取り、baseパッケージをインストールしなおせば復旧できます。

約10分の格闘でした。

以上。