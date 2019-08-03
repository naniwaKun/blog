---
title: apacheからnginxへ移行した話
author: naniwa
type: post
date: 2017-01-22T07:14:41+00:00
excerpt: |
  |
    
    				
    				wordpressをnginxで入れ子にして設定する話
url: /wordpress/500/
categories:
  - サーバー記録

---
もう古い話題なのだが、先日apacheからnginxに移行した。
  
移行理由はwebサーバーを「[let&#8217;s note cf-w4][1] 」から「[DG-STK1B][2]」に移行するにあたりnginx使うか！という安直な発想から。これでシングルコアpenMを卒業したことになる。ふむ。まだまだ使うけどw
  
そこで、wordpressをいくつか持っているのでこれをnginxで動かすには.htaccessをnginxの設定に変換する必要がある。

そこで以下の構成のwordpresを引っ越す必要があった。

http://domain/
  
に設置したWordpressと
  
http://domain/blog/
  
に設置したWordpressの構成

つまり、マトリョーシカのように入れ子のようになっているわけだが、このnginxの設定が日本語でネット上で見つけれなかったので自分の設定を晒すことにする。&#8221;wordpress nginx 入れ子&#8221;で検索すると困っている人のブログが上位に出てくるので誰かの参考になればいいなと思います。

nginx歴が2日なので、無駄設定が散見されるかもしれません。ご容赦ください。

ポイントは環境に合わせてlocationをその都度一から書くということでしょうか。domainとblogの文字列は各自環境に変えてください。

 [1]: http://panasonic.jp/pc/p-db/CF-W4GW9AXR.html
 [2]: https://www.amazon.co.jp/Diginnos-Stick-DG-STK1B-%E3%82%B9%E3%83%86%E3%82%A3%E3%83%83%E3%82%AF%E5%9E%8B%E3%83%91%E3%82%BD%E3%82%B3%E3%83%B3-Windows/dp/B015XU925A