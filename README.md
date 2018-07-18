# Study-js-iOS  

iOS のセンサーを js から値を取って、その値を PC 側で受け取りたい  


---  


### 想定する実装方法  

(1) javascript で web ベースでなんかする  
(2) Swift みたいなもので、iOS のネイティブでなんかする  

→ javascript の方が、気軽に行けそうなので、(1) の方法でやる。  
javascript のサンプルをググると、iPhone のセンサーの値の取得はノータイムでできた。  

次に取得した値を、PC で受け取れるようになんかする必要がある。  

(A) web socket でサーバ経由で、値を送る（node.js とか）  
(B) 取得した値を、サーバ上の JSON ファイルに書き込む。その JSON を PC で読む。  

→ サーバはよくわからないし、環境整えるのも面倒だったら嫌なので、(B) の JSON で。  

調べたところ JSON の書き込みは、javascript では、不可。php ならできる。  
index.php の中で、javascript で値を取得し、php に値を渡して、JSON に書き込もうとした。  

サーバサイド言語のアレなのか知らんけど、php の方が先に実行？、  
javascript から、php への値渡しは、 Ajax とかを使う必要があるっぽい  


javascript のサンプルを見つけた時点で、楽勝かと思ってしまったけど、そんなことはなかった。。。  



---  


### iOS のセンサー一覧  

- 光・音声系  
  - 輝度センサー  
  - 近接センサー  
  - シェイクジェスチャー  
  - マイクの音  

- 位置情報系  
  - 緯度・経度  
  - 電子コンパス  
  - 標高  

- 移動・動作系  
  - 加速度センサー  
  - 歩数・進行状況  
  - 移動速度  

- その他  
  - 顔検出  
  - バッテリー残量  



---  


### php / js のテスト用に python3 で ローカルサーバ を立てる  


```

python3 -m http.server 8000

```

落とす時は、Ctrl + C  



---  

### reference  

[http://blog.koogawa.com/entry/2016/04/30/080000](http://blog.koogawa.com/entry/2016/04/30/080000)  
x - vibration API, html5 / 振動  
o - geolocation API, html5 / 位置情報  
o - deviceorientation Event / 傾き  
o - compass / 方角  
o - device motion / 動き  
x - ambientLight / 明るさ  
x - proximity / 距離  

[https://www.yoheim.net/blog.php?q=20130201](https://www.yoheim.net/blog.php?q=20130201)  

[https://shimz.me/blog/javascript/2872](https://shimz.me/blog/javascript/2872)  
位置、コンパス、ジャイロ、加速度  



