# ISUCON

###### tags: `ISUCON` `private`

[ISUCOの勝ち方のメモ](https://wiki.infra-workshop.tech/event/ISUCON8/ISUCON/ISUCON%E3%81%AE%E5%8B%9D%E3%81%A1%E6%96%B9%E5%8B%95%E7%94%BB%E3%83%A1%E3%83%A2)

## 参考リンク
[ISUCON8 の予選問題を復習した](https://kujira16.hateblo.jp/entry/2018/10/22/013611)
[isucon8の予選の環境構築](https://qiita.com/sora083/items/683a7f0523dba3aa8c19)


## メモ
```=shell
sudo cp /dev/null /var/log/h2o/access.log
/home/isucon/torb/db/init.sh
/home/isucon/torb/bench/bin/bench -remotes=localhsot:80 -output result.json
jq . < result.json 
```

### ベンチマーク
Goの初期実装で743点

```shell=
[isucon@localhost bench]$ jq . < result.json 
{
  "job_id": "",
  "ip_addrs": "172.28.128.4:80",
  "pass": true,
  "score": 743,
  "message": "ok",
  "error": [
    "2020-02-09 13:39:45.516312655 +0000 UTC m=+30.083236019 リクエストがタイムアウトしました (GET /api/users/1697 )",
    "2020-02-09 13:40:02.37860296 +0000 UTC m=+46.945526329 リクエストがタイムアウトしました (GET /api/users/1664 )",
    "2020-02-09 13:40:17.053716423 +0000 UTC m=+61.620639749 リクエストがタイムアウトしました (POST /api/events/11/actions/reserve )",
    "2020-02-09 13:40:17.993109855 +0000 UTC m=+62.560033192 リクエストがタイムアウトしました (GET / )"
  ],
  "log": [
    "02/09 13:39:36 レスポンスが遅いため負荷レベルを上げられませんでした。/api/events/11/actions/reserve",
    "02/09 13:39:37 レスポンスが遅いため負荷レベルを上げられませんでした。/api/events/11/actions/reserve",
    "02/09 13:39:38 レスポンスが遅いため負荷レベルを上げられませんでした。/api/events/11/actions/reserve",
    "02/09 13:39:39 レスポンスが遅いため負荷レベルを上げられませんでした。/api/events/11/actions/reserve",
    "02/09 13:39:40 レスポンスが遅いため負荷レベルを上げられませんでした。/api/events/11/actions/reserve",
    "02/09 13:39:41 レスポンスが遅いため負荷レベルを上げられませんでした。/api/events/11/actions/reserve",
    "02/09 13:39:42 レスポンスが遅いため負荷レベルを上げられませんでした。/api/events/11/actions/reserve",
    "02/09 13:39:43 レスポンスが遅いため負荷レベルを上げられませんでした。/api/events/11/actions/reserve",
    "02/09 13:39:44 レスポンスが遅いため負荷レベルを上げられませんでした。/api/events/11/sheets/C/427/reservation",
    "02/09 13:39:45 エラーが発生したため負荷レベルを上げられませんでした。2020-02-09 13:39:45.516312655 +0000 UTC m=+30.083236019 リクエストがタイムアウトしました (GET /api/users/1697 )",
    "02/09 13:39:46 エラーが発生したため負荷レベルを上げられませんでした。2020-02-09 13:39:45.516312655 +0000 UTC m=+30.083236019 リクエストがタイムアウトしました (GET /api/users/1697 )",
    "02/09 13:39:47 エラーが発生したため負荷レベルを上げられませんでした。2020-02-09 13:39:45.516312655 +0000 UTC m=+30.083236019 リクエストがタイムアウトしました (GET /api/users/1697 )",
    "02/09 13:39:48 エラーが発生したため負荷レベルを上げられませんでした。2020-02-09 13:39:45.516312655 +0000 UTC m=+30.083236019 リクエストがタイムアウトしました (GET /api/users/1697 )",
    "02/09 13:39:49 エラーが発生したため負荷レベルを上げられませんでした。2020-02-09 13:39:45.516312655 +0000 UTC m=+30.083236019 リクエストがタイムアウトしました (GET /api/users/1697 )",
    "02/09 13:39:50 レスポンスが遅いため負荷レベルを上げられませんでした。/api/events/11/actions/reserve",
    "02/09 13:39:51 レスポンスが遅いため負荷レベルを上げられませんでした。/api/events/11/actions/reserve",
    "02/09 13:39:52 レスポンスが遅いため負荷レベルを上げられませんでした。/api/events/11/sheets/C/27/reservation",
    "02/09 13:39:53 レスポンスが遅いため負荷レベルを上げられませんでした。/api/events/10",
    "02/09 13:39:54 レスポンスが遅いため負荷レベルを上げられませんでした。/api/events/11/sheets/C/365/reservation",
    "02/09 13:39:55 レスポンスが遅いため負荷レベルを上げられませんでした。/api/events/11/actions/reserve",
    "02/09 13:39:56 レスポンスが遅いため負荷レベルを上げられませんでした。/",
    "02/09 13:39:57 レスポンスが遅いため負荷レベルを上げられませんでした。/api/events/11/sheets/D/27/reservation",
    "02/09 13:39:58 レスポンスが遅いため負荷レベルを上げられませんでした。/api/events/11/actions/reserve",
    "02/09 13:39:59 レスポンスが遅いため負荷レベルを上げられませんでした。/api/events/11/actions/reserve",
    "02/09 13:40:00 レスポンスが遅いため負荷レベルを上げられませんでした。/api/events/10",
    "02/09 13:40:01 レスポンスが遅いため負荷レベルを上げられませんでした。/api/events/11/actions/reserve",
    "02/09 13:40:02 エラーが発生したため負荷レベルを上げられませんでした。2020-02-09 13:40:02.37860296 +0000 UTC m=+46.945526329 リクエストがタイムアウトしました (GET /api/users/1664 )",
    "02/09 13:40:03 エラーが発生したため負荷レベルを上げられませんでした。2020-02-09 13:40:02.37860296 +0000 UTC m=+46.945526329 リクエストがタイムアウトしました (GET /api/users/1664 )",
    "02/09 13:40:04 エラーが発生したため負荷レベルを上げられませんでした。2020-02-09 13:40:02.37860296 +0000 UTC m=+46.945526329 リクエストがタイムアウトしました (GET /api/users/1664 )",
    "02/09 13:40:05 エラーが発生したため負荷レベルを上げられませんでした。2020-02-09 13:40:02.37860296 +0000 UTC m=+46.945526329 リクエストがタイムアウトしました (GET /api/users/1664 )",
    "02/09 13:40:06 エラーが発生したため負荷レベルを上げられませんでした。2020-02-09 13:40:02.37860296 +0000 UTC m=+46.945526329 リクエストがタイムアウトしました (GET /api/users/1664 )",
    "02/09 13:40:07 レスポンスが遅いため負荷レベルを上げられませんでした。/",
    "02/09 13:40:08 レスポンスが遅いため負荷レベルを上げられませんでした。/api/events/11/actions/reserve",
    "02/09 13:40:09 レスポンスが遅いため負荷レベルを上げられませんでした。/api/events/11/actions/reserve",
    "02/09 13:40:10 レスポンスが遅いため負荷レベルを上げられませんでした。/api/events/11/actions/reserve",
    "02/09 13:40:11 レスポンスが遅いため負荷レベルを上げられませんでした。/api/events/11/actions/reserve",
    "02/09 13:40:12 レスポンスが遅いため負荷レベルを上げられませんでした。/api/events/10",
    "02/09 13:40:13 レスポンスが遅いため負荷レベルを上げられませんでした。/api/events/10",
    "02/09 13:40:14 レスポンスが遅いため負荷レベルを上げられませんでした。/api/events/10",
    "02/09 13:40:15 レスポンスが遅いため負荷レベルを上げられませんでした。/api/events/11/actions/reserve",
    "02/09 13:40:16 レスポンスが遅いため負荷レベルを上げられませんでした。/api/events/11/actions/reserve",
    "02/09 13:40:17 エラーが発生したため負荷レベルを上げられませんでした。2020-02-09 13:40:17.053716423 +0000 UTC m=+61.620639749 リクエストがタイムアウトしました (POST /api/events/11/actions/reserve )"
  ],
  "load_level": 0,
  "start_time": "2020-02-09T13:39:15.748455706Z",
  "end_time": "2020-02-09T13:40:28.732220048Z"
}
```

### Webアプリで起きていることを知る
```=shell
[isucon@localhost etc]$ ss -antup
[isucon@localhost etc]$ ps aux | grep 80
root         1  0.0  0.4 128096  4436 ?        Ss   08:05   0:04 /usr/lib/systemd/systemd --system --deserialize 15
postfix  29088  0.0  0.1  89804  1660 ?        S    13:05   0:00 pickup -l -t unix -u
isucon   29570  0.0  0.0 112716   964 pts/1    S+   14:30   0:00 grep --color=auto 80
root     29855  0.0  0.7 148556  7168 ?        Ss   08:57   0:00 perl -x /usr/share/h2o/start_server --pid-file=/var/run/h2o/h2o.pid --log-file=/var/log/h2o/error.log --port=0.0.0.0:80 -- /usr/sbin/h2o -c /etc/h2o/h2o.conf

[isucon@localhost etc]$ sudo cat /var/log/h2o/error.log
starting new worker 29908
[INFO] raised RLIMIT_NOFILE to 1048576
h2o server (pid:29908) is ready to serve requests
[lib/core/proxy.c] in request:/admin/:I/O timeout
[lib/core/proxy.c] in request:/api/users/3002:I/O timeout
[isucon@localhost etc]$ 
```

#### h2oのconf
```=shell
[isucon@localhost log]$ cat /etc/h2o/h2o.conf
user: isucon

access-log: /var/log/h2o/access.log
error-log: /var/log/h2o/error.log
pid-file: /var/run/h2o/h2o.pid

hosts:
  "localhost:80":
    listen:
      port: 80
      host: 0.0.0.0
    paths:
      "/favicon.ico":
        file.file: /home/isucon/torb/webapp/static/favicon.ico
      "/css":
        file.dir: /home/isucon/torb/webapp/static/css
      "/img":
        file.dir: /home/isucon/torb/webapp/static/img
      "/js":
        file.dir: /home/isucon/torb/webapp/static/js
      "/":
        proxy.reverse.url: http://127.0.0.1:8080/
        proxy.preserve-host: ON
[isucon@localhost log]$ 
```


#### アクセスログをみる
* ログの見方がわからないから調べる
* 確かログを可視化するツールがあったはず

```=shell
[isucon@localhost log]$ sudo less /var/log/h2o/access.log | head -n 5
172.28.128.1 - - [09/Feb/2020:09:09:03 +0000] "GET / HTTP/1.1" 200 14195 "-" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_12_6) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/79.0.3945.130 Safari/537.36"
172.28.128.1 - - [09/Feb/2020:09:09:05 +0000] "GET /css/bootstrap.min.css HTTP/1.1" 200 140930 "http://172.28.128.4/" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_12_6) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/79.0.3945.130 Safari/537.36"
172.28.128.1 - - [09/Feb/2020:09:09:05 +0000] "GET /js/vue.min.js HTTP/1.1" 200 86452 "http://172.28.128.4/" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_12_6) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/79.0.3945.130 Safari/537.36"
172.28.128.1 - - [09/Feb/2020:09:09:05 +0000] "GET /js/bootstrap-waitingfor.min.js HTTP/1.1" 200 2074 "http://172.28.128.4/" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_12_6) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/79.0.3945.130 Safari/537.36"
172.28.128.1 - - [09/Feb/2020:09:09:05 +0000] "GET /js/bootstrap.bundle.min.js HTTP/1.1" 200 70682 "http://172.28.128.4/" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_12_6) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/79.0.3945.130 Safari/537.36"
[isucon@localhost log]$ 
```
取り敢えず記事で紹介されているものを試してみる
https://qiita.com/dharada1/items/bae934d11765171c80d5

本番はログをalpに食わせるためにフォーマットを変えて上げる必要がある
https://qiita.com/dharada1/items/bae934d11765171c80d5


/etc/h2o/h2o.confを書き換えて、accecc.logの形式を変更
```=shell
[isucon@localhost h2o]$ diff  /etc/h2o/h2o.conf /etc/h2o/h2o.conf.org 
3,5c3
< access-log:
<   path: /var/log/h2o/access.log
<   format: "time:%t\thost:%h\tua:\"%{User-agent}i\"\tstatus:%s\treq:%r\turi:%U\treqtime:%{duration}x\tsize:%b\tmethod:%m\t"
---
> access-log: /var/log/h2o/access.log
```

confをリロード
```=shell
[isucon@localhost h2o]$ sudo systemctl reload h2o
[isucon@localhost h2o]$ sudo systemctl status h2o
● h2o.service - H2O - the optimized HTTP/1, HTTP/2 server
   Loaded: loaded (/usr/lib/systemd/system/h2o.service; enabled; vendor preset: disabled)
   Active: active (running) since Sun 2020-02-09 08:57:35 UTC; 8h ago
  Process: 32036 ExecReload=/bin/kill -HUP ${MAINPID} (code=exited, status=0/SUCCESS)
 Main PID: 29855 (perl)
   CGroup: /system.slice/h2o.service
           ├─29855 perl -x /usr/share/h2o/start_server --pid-file=/var/run/h2o/h2o.pid ...
           ├─32037 /usr/sbin/h2o -c /etc/h2o/h2o.conf
           └─32038 perl -x /usr/share/h2o/annotate-backtrace-symbols

Feb 09 08:57:35 localhost.localdomain systemd[1]: Started H2O - the optimized HTTP/1, ....
Feb 09 08:57:36 localhost.localdomain h2o[29855]: start_server (pid:29855) starting now...
Feb 09 16:57:19 localhost.localdomain systemd[1]: Reloading H2O - the optimized HTTP/1....
Feb 09 16:57:19 localhost.localdomain systemd[1]: Reloaded H2O - the optimized HTTP/1,....
Feb 09 17:13:12 localhost.localdomain systemd[1]: Reloading H2O - the optimized HTTP/1....
Feb 09 17:13:12 localhost.localdomain systemd[1]: Reloaded H2O - the optimized HTTP/1,....
Feb 09 17:17:50 localhost.localdomain systemd[1]: Reloading H2O - the optimized HTTP/1....
Feb 09 17:17:50 localhost.localdomain systemd[1]: Reloaded H2O - the optimized HTTP/1,....
Hint: Some lines were ellipsized, use -l to show in full.
[isucon@localhost h2o]$ 
```

logを消去、DBを初期化して再実行
```=shell
sudo cp /dev/null /var/log/h2o/access.log
/home/isucon/torb/db/init.sh
/home/isucon/torb/bench/bin/bench -remotes=172.28.128.4:80 -output result.json
jq . < result.json 
```
フォーマット変わった
```=shell
[isucon@localhost h2o]$ sudo cat /var/log/h2o/access.log | tail -n 5
time:[09/Feb/2020:17:22:53 +0000]	host:172.28.128.4	ua:"isucon8q-benchmarker"	status:200	req:GET / HTTP/1.1	uri:/	reqtime:12.028336	size:14677	method:GET	
time:[09/Feb/2020:17:22:35 +0000]	host:172.28.128.4	ua:"isucon8q-benchmarker"	status:502	req:GET /api/users/109 HTTP/1.1	uri:/api/users/109	reqtime:30.000008	size:11	method:GET	
time:[09/Feb/2020:17:22:57 +0000]	host:172.28.128.4	ua:"isucon8q-benchmarker"	status:200	req:GET / HTTP/1.1	uri:/	reqtime:9.639571	size:14677	method:GET	
time:[09/Feb/2020:17:23:00 +0000]	host:172.28.128.4	ua:"isucon8q-benchmarker"	status:200	req:GET /admin/api/reports/sales HTTP/1.1	uri:/admin/api/reports/sales	reqtime:12.384262	size:14983624	method:GET	
time:[09/Feb/2020:17:22:47 +0000]	host:172.28.128.4	ua:"isucon8q-benchmarker"	status:200	req:GET /api/users/3185 HTTP/1.1	uri:/api/users/3185	reqtime:28.669228	size:2393	method:GET	
[isucon@localhost h2o]$ 
```

alpをインストール
https://nishinatoshiharu.com/install-alp-to-nginx/#nginxalp

wgetなかったので前準備から
```=shell
[isucon@localhost src]$ cd /usr/local/src/
[isucon@localhost h2o]$ sudo wget https://github.com/tkuchiki/alp/releases/download/v0.3.1/alp_linux_amd64.zip
sudo: wget: command not found
[isucon@localhost h2o]$ sudo yum -y install wget
...
Complete!
[isucon@localhost h2o]$ sudo wget https://github.com/tkuchiki/alp/releases/download/v0.3.1/alp_linux_amd64.zip
...
2020-02-09 17:32:13 (500 KB/s) - ‘alp_linux_amd64.zip’ saved [1872682/1872682]
[isucon@localhost h2o]$ 
[isucon@localhost h2o]$ sudo unzip alp_linux_amd64.zip
Archive:  alp_linux_amd64.zip
  inflating: alp                     
[isucon@localhost h2o]$ sudo install ./alp /usr/local/bin
````

alpの実行できない...
```=shell
[isucon@localhost src]$ sudo ./alp 
2020/02/09 17:47:16 open : no such file or directory
[isucon@localhost src]$ file alp
alp: ELF 64-bit LSB executable, x86-64, version 1 (SYSV), statically linked, not stripped
[isucon@localhost src]$ uname -a
Linux localhost.localdomain 3.10.0-957.12.2.el7.x86_64 #1 SMP Tue May 14 21:24:32 UTC 2019 x86_64 x86_64 x86_64 GNU/Linux
[isucon@localhost src]$ sudo wget https://github.com/tkuchiki/alp/releases/download/v1.0.3/alp_linux_amd64.zip

```

### Goを読むための環境構築
vagrantのプラグインで共有フォルダを指定
https://qiita.com/centipede/items/5b3cb4965618993cefec
上のせいで再構築するはめに.....
https://qiita.com/pyon_kiti_jp/items/05eb45f611ee7ccab1e1

再構築
https://qiita.com/shuntakeuch1/items/5a4b54297d5626b5bd32

実際起動されている時にどういう挙動をしているかを可視化するツールを試してみる

pprofのインストール
```=shell
[isucon@localhost ~]$ go version
go version go1.10.3 linux/amd64
[isucon@localhost ~]$ go get -u github.com/google/pprof
```

graphvizのインストール
```=shell
[isucon@localhost ~]$ sudo yum install graphviz
```

下記サイトを参考に、go.appに埋め込み
https://medium.com/eureka-engineering/go%E8%A8%80%E8%AA%9E%E3%81%AE%E3%83%97%E3%83%AD%E3%83%95%E3%82%A1%E3%82%A4%E3%83%AA%E3%83%B3%E3%82%B0%E3%83%84%E3%83%BC%E3%83%AB-pprof%E3%81%AEweb-ui%E3%81%8C%E3%82%81%E3%81%A1%E3%82%83%E3%81%8F%E3%81%A1%E3%82%83%E4%BE%BF%E5%88%A9%E3%81%AA%E3%81%AE%E3%81%A7%E7%B4%B9%E4%BB%8B%E3%81%99%E3%82%8B-6a34a489c9ee

対象ファイルってこれなのね
```=shell
[isucon@localhost torb]$ pwd
/home/isucon/torb/webapp/go/src/torb
[isucon@localhost torb]$ ll
total 56
-rw-r--r--. 1 isucon isucon 26388 Feb 17 10:02 app.go
-rw-r--r--. 1 isucon isucon 26388 Feb 17 10:02 app.go.org
[isucon@localhost torb]$ 
```

ファイルを変える前にsnapshotを取得
```=shell
tatsuta@mac: vagrant halt                                    (git)-[master]
==> default: Attempting graceful shutdown of VM...
tatsuta@mac: vagrant snapshot save init                      (git)-[master]
==> default: Snapshotting the machine as 'init'...
==> default: Snapshot saved! You can restore the snapshot at any time by
==> default: using `vagrant snapshot restore`. You can delete it using
==> default: `vagrant snapshot delete`.
tatsuta@mac: vagrant snapshot list                           (git)-[master]
init
```

変更&make
```=shell
[isucon@localhost go]$ diff src/torb/app.go src/torb/app.go.org 
18d17
< 	_ "net/http/pprof"
314,317d312
< 	go func() {
< 		log.Println(http.ListenAndServe("localhost:80", nil))
< 	}()
< 
[isucon@localhost go]$ sudo vi src/torb/app.go
[isucon@localhost go]$ make
GOPATH=`pwd`:`pwd`/vendor go build -v torb
torb

```

変更コード(import, mainを追加)
```=go
        "net/http"
        _ "net/http/pprof"
        
func main() {
        go func() {
                log.Println(http.ListenAndServe("localhost:80", nil))
        }()


```


再起動
```=shell
[isucon@localhost go]$ sudo systemctl  restart torb.go.service
[isucon@localhost go]$ sudo systemctl status torb.go.service
● torb.go.service - isucon8 qualifier webapp in go
   Loaded: loaded (/etc/systemd/system/torb.go.service; enabled; vendor preset: disabled)
   Active: active (running) since Mon 2020-02-17 11:52:44 UTC; 8s ago
 Main PID: 3878 (torb)
   CGroup: /system.slice/torb.go.service
           └─3878 /home/isucon/torb/webapp/go/torb

Feb 17 11:52:44 localhost.localdomain torb[3878]: ____    __
Feb 17 11:52:44 localhost.localdomain torb[3878]: / __/___/ /  ___
Feb 17 11:52:44 localhost.localdomain torb[3878]: / _// __/ _ \/ _ \
Feb 17 11:52:44 localhost.localdomain torb[3878]: /___/\__/_//_/\___/ v3....
Feb 17 11:52:44 localhost.localdomain torb[3878]: High performance, minim...
Feb 17 11:52:44 localhost.localdomain torb[3878]: https://echo.labstack.com
Feb 17 11:52:44 localhost.localdomain torb[3878]: _______________________...
Feb 17 11:52:44 localhost.localdomain torb[3878]: O\
Feb 17 11:52:44 localhost.localdomain torb[3878]: ⇨ http server started o…80
Feb 17 11:52:44 localhost.localdomain torb[3878]: 2020/02/17 11:52:44 lis...
Hint: Some lines were ellipsized, use -l to show in full.
[isucon@localhost go]$ 

```

http://nakawatch.hatenablog.com/entry/2018/10/21/005458

https://christina04.hatenablog.com/entry/golang-pprof-cli

http://blog.keepdata.jp/entry/2018/07/23/104720

https://golang.org/pkg/net/http/pprof/

make
```=shell
[isucon@localhost go]$ make
GOPATH=`pwd`:`pwd`/vendor go build -v torb
github.com/go-sql-driver/mysql
github.com/gorilla/context
github.com/gorilla/securecookie
github.com/gorilla/sessions
github.com/mattn/go-isatty
github.com/mattn/go-colorable
github.com/labstack/gommon/color
github.com/valyala/fasttemplate/vendor/github.com/valyala/bytebufferpool
github.com/valyala/fasttemplate
github.com/labstack/gommon/log
golang.org/x/crypto/acme
golang.org/x/crypto/acme/autocert
github.com/labstack/echo
github.com/dgrijalva/jwt-go
github.com/labstack/gommon/bytes
github.com/labstack/gommon/random
github.com/labstack/echo/middleware
github.com/labstack/echo-contrib/session
torb
[isucon@localhost go]$ pwd
/home/isucon/torb/webapp/go
[isucon@localhost go]$ 

```




```=shell
[isucon@localhost go]$ go tool pprof http://localhost:6060/debug/pprof/profile 
Fetching profile over HTTP from http://localhost:6060/debug/pprof/profile
http://localhost:6060/debug/pprof/profile: Get http://localhost:6060/debug/pprof/profile: dial tcp [::1]:6060: connect: connection refused
failed to fetch any source profiles
[isucon@localhost go]$ 
```


計測用コマンド
```=shell
go tool pprof http://localhost:6060/debug/pprof/profile?seconds=90
/home/isucon/torb/bench/bin/bench -remotes=localhost:80 -output result.json
```

top
```=shell
(pprof) top
Showing nodes accounting for 6010ms, 57.96% of 10370ms total
Dropped 173 nodes (cum <= 51.85ms)
Showing top 10 nodes out of 159
      flat  flat%   sum%        cum   cum%
    3600ms 34.72% 34.72%     3770ms 36.35%  syscall.Syscall
     710ms  6.85% 41.56%      710ms  6.85%  runtime.epollwait
     440ms  4.24% 45.81%      990ms  9.55%  runtime.mallocgc
     260ms  2.51% 48.31%      390ms  3.76%  runtime.scanobject
     190ms  1.83% 50.14%      790ms  7.62%  database/sql.convertAssign
     190ms  1.83% 51.98%      190ms  1.83%  runtime.heapBitsSetType
     170ms  1.64% 53.62%      170ms  1.64%  runtime.memmove
     170ms  1.64% 55.26%      170ms  1.64%  runtime.usleep
     150ms  1.45% 56.70%      150ms  1.45%  runtime.futex
     130ms  1.25% 57.96%      130ms  1.25%  runtime.heapBitsForObject
(pprof) 
```

list mainの結果
get eventの処理に時間がかかっていることがわかるが....
可読性悪い

```shell
(pprof) list main
Total: 10.37s
ROUTINE ======================== main.adminLoginRequired.func1 in /home/isucon/torb/webapp/go/src/torb/app.go
         0      2.60s (flat, cum) 25.07% of Total
         .          .    160:func adminLoginRequired(next echo.HandlerFunc) echo.HandlerFunc {
         .          .    161:	return func(c echo.Context) error {
         .          .    162:		if _, err := getLoginAdministrator(c); err != nil {
         .          .    163:			return resError(c, "admin_login_required", 401)
         .          .    164:		}
         .      2.60s    165:		return next(c)
         .          .    166:	}
         .          .    167:}
         .          .    168:
         .          .    169:func getLoginUser(c echo.Context) (*User, error) {
         .          .    170:	userID := sessUserID(c)
ROUTINE ======================== main.fillinAdministrator.func1 in /home/isucon/torb/webapp/go/src/torb/app.go
         0      1.70s (flat, cum) 16.39% of Total
         .          .    289:func fillinAdministrator(next echo.HandlerFunc) echo.HandlerFunc {
         .          .    290:	return func(c echo.Context) error {
         .          .    291:		if administrator, err := getLoginAdministrator(c); err == nil {
         .          .    292:			c.Set("administrator", administrator)
         .          .    293:		}
         .      1.70s    294:		return next(c)
         .          .    295:	}
         .          .    296:}
         .          .    297:
         .          .    298:func validateRank(rank string) bool {
         .          .    299:	var count int
ROUTINE ======================== main.fillinUser.func1 in /home/isucon/torb/webapp/go/src/torb/app.go
         0      1.97s (flat, cum) 19.00% of Total
         .          .    280:func fillinUser(next echo.HandlerFunc) echo.HandlerFunc {
         .          .    281:	return func(c echo.Context) error {
         .          .    282:		if user, err := getLoginUser(c); err == nil {
         .          .    283:			c.Set("user", user)
         .          .    284:		}
         .      1.97s    285:		return next(c)
         .          .    286:	}
         .          .    287:}
         .          .    288:
         .          .    289:func fillinAdministrator(next echo.HandlerFunc) echo.HandlerFunc {
         .          .    290:	return func(c echo.Context) error {
ROUTINE ======================== main.getEvent in /home/isucon/torb/webapp/go/src/torb/app.go
      50ms      6.17s (flat, cum) 59.50% of Total
         .          .    239:	if err != nil {
         .          .    240:		return nil, err
         .          .    241:	}
         .          .    242:	defer rows.Close()
         .          .    243:
      10ms      140ms    244:	for rows.Next() {
         .       30ms    245:		var sheet Sheet
         .      140ms    246:		if err := rows.Scan(&sheet.ID, &sheet.Rank, &sheet.Num, &sheet.Price); err != nil {
         .          .    247:			return nil, err
         .          .    248:		}
         .          .    249:		event.Sheets[sheet.Rank].Price = event.Price + sheet.Price
         .          .    250:		event.Total++
         .       10ms    251:		event.Sheets[sheet.Rank].Total++
         .          .    252:
         .       70ms    253:		var reservation Reservation
      10ms      5.72s    254:		err := db.QueryRow("SELECT * FROM reservations WHERE event_id = ? AND sheet_id = ? AND canceled_at IS NULL GROUP BY event_id, sheet_id HAVING reserved_at = MIN(reserved_at)", event.ID, sheet.ID).Scan(&reservation.ID, &reservation.EventID, &reservation.SheetID, &reservation.UserID, &reservation.ReservedAt, &reservation.CanceledAt)
         .          .    255:		if err == nil {
         .          .    256:			sheet.Mine = reservation.UserID == loginUserID
         .          .    257:			sheet.Reserved = true
         .          .    258:			sheet.ReservedAtUnix = reservation.ReservedAt.Unix()
         .          .    259:		} else if err == sql.ErrNoRows {
         .          .    260:			event.Remains++
      10ms       20ms    261:			event.Sheets[sheet.Rank].Remains++
         .          .    262:		} else {
         .          .    263:			return nil, err
         .          .    264:		}
         .          .    265:
      20ms       40ms    266:		event.Sheets[sheet.Rank].Detail = append(event.Sheets[sheet.Rank].Detail, &sheet)
         .          .    267:	}
         .          .    268:
         .          .    269:	return &event, nil
         .          .    270:}
         .          .    271:
ROUTINE ======================== main.getEvents in /home/isucon/torb/webapp/go/src/torb/app.go
         0      3.67s (flat, cum) 35.39% of Total
         .          .    191:	if err != nil {
         .          .    192:		return nil, err
         .          .    193:	}
         .          .    194:	defer tx.Commit()
         .          .    195:
         .       10ms    196:	rows, err := tx.Query("SELECT * FROM events ORDER BY id ASC")
         .          .    197:	if err != nil {
         .          .    198:		return nil, err
         .          .    199:	}
         .          .    200:	defer rows.Close()
         .          .    201:
         .          .    202:	var events []*Event
         .          .    203:	for rows.Next() {
         .          .    204:		var event Event
         .          .    205:		if err := rows.Scan(&event.ID, &event.Title, &event.PublicFg, &event.ClosedFg, &event.Price); err != nil {
         .          .    206:			return nil, err
         .          .    207:		}
         .          .    208:		if !all && !event.PublicFg {
         .          .    209:			continue
         .          .    210:		}
         .          .    211:		events = append(events, &event)
         .          .    212:	}
         .          .    213:	for i, v := range events {
         .      3.66s    214:		event, err := getEvent(v.ID, -1)
         .          .    215:		if err != nil {
         .          .    216:			return nil, err
         .          .    217:		}
         .          .    218:		for k := range event.Sheets {
         .          .    219:			event.Sheets[k].Detail = nil
ROUTINE ======================== main.getLoginAdministrator in /home/isucon/torb/webapp/go/src/torb/app.go
         0       10ms (flat, cum) 0.096% of Total
         .          .    180:	administratorID := sessAdministratorID(c)
         .          .    181:	if administratorID == 0 {
         .          .    182:		return nil, errors.New("not logged in")
         .          .    183:	}
         .          .    184:	var administrator Administrator
         .       10ms    185:	err := db.QueryRow("SELECT id, nickname FROM administrators WHERE id = ?", administratorID).Scan(&administrator.ID, &administrator.Nickname)
         .          .    186:	return &administrator, err
         .          .    187:}
         .          .    188:
         .          .    189:func getEvents(all bool) ([]*Event, error) {
         .          .    190:	tx, err := db.Begin()
ROUTINE ======================== main.loginRequired.func1 in /home/isucon/torb/webapp/go/src/torb/app.go
         0      1.42s (flat, cum) 13.69% of Total
         .          .    151:func loginRequired(next echo.HandlerFunc) echo.HandlerFunc {
         .          .    152:	return func(c echo.Context) error {
         .          .    153:		if _, err := getLoginUser(c); err != nil {
         .          .    154:			return resError(c, "login_required", 401)
         .          .    155:		}
         .      1.42s    156:		return next(c)
         .          .    157:	}
         .          .    158:}
         .          .    159:
         .          .    160:func adminLoginRequired(next echo.HandlerFunc) echo.HandlerFunc {
         .          .    161:	return func(c echo.Context) error {
ROUTINE ======================== main.main.func10 in /home/isucon/torb/webapp/go/src/torb/app.go
         0      670ms (flat, cum)  6.46% of Total
         .          .    549:		loginUserID := int64(-1)
         .          .    550:		if user, err := getLoginUser(c); err == nil {
         .          .    551:			loginUserID = user.ID
         .          .    552:		}
         .          .    553:
         .      670ms    554:		event, err := getEvent(eventID, loginUserID)
         .          .    555:		if err != nil {
         .          .    556:			if err == sql.ErrNoRows {
         .          .    557:				return resError(c, "not_found", 404)
         .          .    558:			}
         .          .    559:			return err
ROUTINE ======================== main.main.func11 in /home/isucon/torb/webapp/go/src/torb/app.go
         0      430ms (flat, cum)  4.15% of Total
         .          .    575:		user, err := getLoginUser(c)
         .          .    576:		if err != nil {
         .          .    577:			return err
         .          .    578:		}
         .          .    579:
         .      430ms    580:		event, err := getEvent(eventID, user.ID)
         .          .    581:		if err != nil {
         .          .    582:			if err == sql.ErrNoRows {
         .          .    583:				return resError(c, "invalid_event", 404)
         .          .    584:			}
         .          .    585:			return err
ROUTINE ======================== main.main.func12 in /home/isucon/torb/webapp/go/src/torb/app.go
         0      330ms (flat, cum)  3.18% of Total
         .          .    643:		user, err := getLoginUser(c)
         .          .    644:		if err != nil {
         .          .    645:			return err
         .          .    646:		}
         .          .    647:
         .      330ms    648:		event, err := getEvent(eventID, user.ID)
         .          .    649:		if err != nil {
         .          .    650:			if err == sql.ErrNoRows {
         .          .    651:				return resError(c, "invalid_event", 404)
         .          .    652:			}
         .          .    653:			return err
ROUTINE ======================== main.main.func13 in /home/isucon/torb/webapp/go/src/torb/app.go
         0      1.70s (flat, cum) 16.39% of Total
         .          .    699:	e.GET("/admin/", func(c echo.Context) error {
         .          .    700:		var events []*Event
         .          .    701:		administrator := c.Get("administrator")
         .          .    702:		if administrator != nil {
         .          .    703:			var err error
         .      1.70s    704:			if events, err = getEvents(true); err != nil {
         .          .    705:				return err
         .          .    706:			}
         .          .    707:		}
         .          .    708:		return c.Render(200, "admin.tmpl", echo.Map{
         .          .    709:			"events":        events,
ROUTINE ======================== main.main.func14 in /home/isucon/torb/webapp/go/src/torb/app.go
         0       10ms (flat, cum) 0.096% of Total
         .          .    733:		if administrator.PassHash != passHash {
         .          .    734:			return resError(c, "authentication_failed", 401)
         .          .    735:		}
         .          .    736:
         .          .    737:		sessSetAdministratorID(c, administrator.ID)
         .       10ms    738:		administrator, err = getLoginAdministrator(c)
         .          .    739:		if err != nil {
         .          .    740:			return err
         .          .    741:		}
         .          .    742:		return c.JSON(200, administrator)
         .          .    743:	})
ROUTINE ======================== main.main.func17 in /home/isucon/torb/webapp/go/src/torb/app.go
         0       70ms (flat, cum)  0.68% of Total
         .          .    777:		}
         .          .    778:		if err := tx.Commit(); err != nil {
         .          .    779:			return err
         .          .    780:		}
         .          .    781:
         .       70ms    782:		event, err := getEvent(eventID, -1)
         .          .    783:		if err != nil {
         .          .    784:			return err
         .          .    785:		}
         .          .    786:		return c.JSON(200, event)
         .          .    787:	}, adminLoginRequired)
ROUTINE ======================== main.main.func18 in /home/isucon/torb/webapp/go/src/torb/app.go
         0       70ms (flat, cum)  0.68% of Total
         .          .    788:	e.GET("/admin/api/events/:id", func(c echo.Context) error {
         .          .    789:		eventID, err := strconv.ParseInt(c.Param("id"), 10, 64)
         .          .    790:		if err != nil {
         .          .    791:			return resError(c, "not_found", 404)
         .          .    792:		}
         .       70ms    793:		event, err := getEvent(eventID, -1)
         .          .    794:		if err != nil {
         .          .    795:			if err == sql.ErrNoRows {
         .          .    796:				return resError(c, "not_found", 404)
         .          .    797:			}
         .          .    798:			return err
ROUTINE ======================== main.main.func19 in /home/isucon/torb/webapp/go/src/torb/app.go
         0      120ms (flat, cum)  1.16% of Total
         .          .    812:		c.Bind(&params)
         .          .    813:		if params.Closed {
         .          .    814:			params.Public = false
         .          .    815:		}
         .          .    816:
         .       30ms    817:		event, err := getEvent(eventID, -1)
         .          .    818:		if err != nil {
         .          .    819:			if err == sql.ErrNoRows {
         .          .    820:				return resError(c, "not_found", 404)
         .          .    821:			}
         .          .    822:			return err
         .          .    823:		}
         .          .    824:
         .          .    825:		if event.ClosedFg {
         .          .    826:			return resError(c, "cannot_edit_closed_event", 400)
         .          .    827:		} else if event.PublicFg && params.Closed {
         .          .    828:			return resError(c, "cannot_close_public_event", 400)
         .          .    829:		}
         .          .    830:
         .          .    831:		tx, err := db.Begin()
         .          .    832:		if err != nil {
         .          .    833:			return err
         .          .    834:		}
         .          .    835:		if _, err := tx.Exec("UPDATE events SET public_fg = ?, closed_fg = ? WHERE id = ?", params.Public, params.Closed, event.ID); err != nil {
         .          .    836:			tx.Rollback()
         .          .    837:			return err
         .          .    838:		}
         .          .    839:		if err := tx.Commit(); err != nil {
         .          .    840:			return err
         .          .    841:		}
         .          .    842:
         .       90ms    843:		e, err := getEvent(eventID, -1)
         .          .    844:		if err != nil {
         .          .    845:			return err
         .          .    846:		}
         .          .    847:		c.JSON(200, e)
         .          .    848:		return nil
ROUTINE ======================== main.main.func20 in /home/isucon/torb/webapp/go/src/torb/app.go
         0      240ms (flat, cum)  2.31% of Total
         .          .    851:		eventID, err := strconv.ParseInt(c.Param("id"), 10, 64)
         .          .    852:		if err != nil {
         .          .    853:			return resError(c, "not_found", 404)
         .          .    854:		}
         .          .    855:
         .      160ms    856:		event, err := getEvent(eventID, -1)
         .          .    857:		if err != nil {
         .          .    858:			return err
         .          .    859:		}
         .          .    860:
         .          .    861:		rows, err := db.Query("SELECT r.*, s.rank AS sheet_rank, s.num AS sheet_num, s.price AS sheet_price, e.price AS event_price FROM reservations r INNER JOIN sheets s ON s.id = r.sheet_id INNER JOIN events e ON e.id = r.event_id WHERE r.event_id = ? ORDER BY reserved_at ASC FOR UPDATE", event.ID)
         .          .    862:		if err != nil {
         .          .    863:			return err
         .          .    864:		}
         .          .    865:		defer rows.Close()
         .          .    866:
         .          .    867:		var reports []Report
         .       10ms    868:		for rows.Next() {
         .          .    869:			var reservation Reservation
         .          .    870:			var sheet Sheet
         .       10ms    871:			if err := rows.Scan(&reservation.ID, &reservation.EventID, &reservation.SheetID, &reservation.UserID, &reservation.ReservedAt, &reservation.CanceledAt, &sheet.Rank, &sheet.Num, &sheet.Price, &event.Price); err != nil {
         .          .    872:				return err
         .          .    873:			}
         .          .    874:			report := Report{
         .          .    875:				ReservationID: reservation.ID,
         .          .    876:				EventID:       event.ID,
         .          .    877:				Rank:          sheet.Rank,
         .          .    878:				Num:           sheet.Num,
         .          .    879:				UserID:        reservation.UserID,
         .          .    880:				SoldAt:        reservation.ReservedAt.Format("2006-01-02T15:04:05.000000Z"),
         .          .    881:				Price:         event.Price + sheet.Price,
         .          .    882:			}
         .          .    883:			if reservation.CanceledAt != nil {
         .       20ms    884:				report.CanceledAt = reservation.CanceledAt.Format("2006-01-02T15:04:05.000000Z")
         .          .    885:			}
         .       10ms    886:			reports = append(reports, report)
         .          .    887:		}
         .       30ms    888:		return renderReportCSV(c, reports)
         .          .    889:	}, adminLoginRequired)
         .          .    890:	e.GET("/admin/api/reports/sales", func(c echo.Context) error {
         .          .    891:		rows, err := db.Query("select r.*, s.rank as sheet_rank, s.num as sheet_num, s.price as sheet_price, e.id as event_id, e.price as event_price from reservations r inner join sheets s on s.id = r.sheet_id inner join events e on e.id = r.event_id order by reserved_at asc for update")
         .          .    892:		if err != nil {
         .          .    893:			return err
ROUTINE ======================== main.main.func21 in /home/isucon/torb/webapp/go/src/torb/app.go
         0      2.10s (flat, cum) 20.25% of Total
         .          .    893:			return err
         .          .    894:		}
         .          .    895:		defer rows.Close()
         .          .    896:
         .          .    897:		var reports []Report
         .      710ms    898:		for rows.Next() {
         .       50ms    899:			var reservation Reservation
         .       50ms    900:			var sheet Sheet
         .          .    901:			var event Event
         .      560ms    902:			if err := rows.Scan(&reservation.ID, &reservation.EventID, &reservation.SheetID, &reservation.UserID, &reservation.ReservedAt, &reservation.CanceledAt, &sheet.Rank, &sheet.Num, &sheet.Price, &event.ID, &event.Price); err != nil {
         .          .    903:				return err
         .          .    904:			}
         .          .    905:			report := Report{
         .          .    906:				ReservationID: reservation.ID,
         .          .    907:				EventID:       event.ID,
         .          .    908:				Rank:          sheet.Rank,
         .          .    909:				Num:           sheet.Num,
         .          .    910:				UserID:        reservation.UserID,
         .      160ms    911:				SoldAt:        reservation.ReservedAt.Format("2006-01-02T15:04:05.000000Z"),
         .          .    912:				Price:         event.Price + sheet.Price,
         .          .    913:			}
         .          .    914:			if reservation.CanceledAt != nil {
         .       90ms    915:				report.CanceledAt = reservation.CanceledAt.Format("2006-01-02T15:04:05.000000Z")
         .          .    916:			}
         .      100ms    917:			reports = append(reports, report)
         .          .    918:		}
         .      380ms    919:		return renderReportCSV(c, reports)
         .          .    920:	}, adminLoginRequired)
         .          .    921:
         .          .    922:	e.Start(":8080")
         .          .    923:}
         .          .    924:
ROUTINE ======================== main.main.func3 in /home/isucon/torb/webapp/go/src/torb/app.go
         0      1.97s (flat, cum) 19.00% of Total
         .          .    340:	}
         .          .    341:	e.Use(session.Middleware(sessions.NewCookieStore([]byte("secret"))))
         .          .    342:	e.Use(middleware.LoggerWithConfig(middleware.LoggerConfig{Output: os.Stderr}))
         .          .    343:	e.Static("/", "public")
         .          .    344:	e.GET("/", func(c echo.Context) error {
         .      1.97s    345:		events, err := getEvents(false)
         .          .    346:		if err != nil {
         .          .    347:			return err
         .          .    348:		}
         .          .    349:		for i, v := range events {
         .          .    350:			events[i] = sanitizeEvent(v)
ROUTINE ======================== main.main.func6 in /home/isucon/torb/webapp/go/src/torb/app.go
         0      660ms (flat, cum)  6.36% of Total
         .          .    433:			var sheet Sheet
         .          .    434:			if err := rows.Scan(&reservation.ID, &reservation.EventID, &reservation.SheetID, &reservation.UserID, &reservation.ReservedAt, &reservation.CanceledAt, &sheet.Rank, &sheet.Num); err != nil {
         .          .    435:				return err
         .          .    436:			}
         .          .    437:
         .      360ms    438:			event, err := getEvent(reservation.EventID, -1)
         .          .    439:			if err != nil {
         .          .    440:				return err
         .          .    441:			}
         .          .    442:			price := event.Sheets[sheet.Rank].Price
         .          .    443:			event.Sheets = nil
         .          .    444:			event.Total = 0
         .          .    445:			event.Remains = 0
         .          .    446:
         .          .    447:			reservation.Event = event
         .          .    448:			reservation.SheetRank = sheet.Rank
         .          .    449:			reservation.SheetNum = sheet.Num
         .          .    450:			reservation.Price = price
         .          .    451:			reservation.ReservedAtUnix = reservation.ReservedAt.Unix()
         .          .    452:			if reservation.CanceledAt != nil {
         .          .    453:				reservation.CanceledAtUnix = reservation.CanceledAt.Unix()
         .          .    454:			}
         .          .    455:			recentReservations = append(recentReservations, reservation)
         .          .    456:		}
         .          .    457:		if recentReservations == nil {
         .          .    458:			recentReservations = make([]Reservation, 0)
         .          .    459:		}
         .          .    460:
         .          .    461:		var totalPrice int
         .          .    462:		if err := db.QueryRow("SELECT IFNULL(SUM(e.price + s.price), 0) FROM reservations r INNER JOIN sheets s ON s.id = r.sheet_id INNER JOIN events e ON e.id = r.event_id WHERE r.user_id = ? AND r.canceled_at IS NULL", user.ID).Scan(&totalPrice); err != nil {
         .          .    463:			return err
         .          .    464:		}
         .          .    465:
         .          .    466:		rows, err = db.Query("SELECT event_id FROM reservations WHERE user_id = ? GROUP BY event_id ORDER BY MAX(IFNULL(canceled_at, reserved_at)) DESC LIMIT 5", user.ID)
         .          .    467:		if err != nil {
         .          .    468:			return err
         .          .    469:		}
         .          .    470:		defer rows.Close()
         .          .    471:
         .          .    472:		var recentEvents []*Event
         .          .    473:		for rows.Next() {
         .          .    474:			var eventID int64
         .          .    475:			if err := rows.Scan(&eventID); err != nil {
         .          .    476:				return err
         .          .    477:			}
         .      300ms    478:			event, err := getEvent(eventID, -1)
         .          .    479:			if err != nil {
         .          .    480:				return err
         .          .    481:			}
         .          .    482:			for k := range event.Sheets {
         .          .    483:				event.Sheets[k].Detail = nil
ROUTINE ======================== main.renderReportCSV in /home/isucon/torb/webapp/go/src/torb/app.go
         0      410ms (flat, cum)  3.95% of Total
         .          .    932:	CanceledAt    string
         .          .    933:	Price         int64
         .          .    934:}
         .          .    935:
         .          .    936:func renderReportCSV(c echo.Context, reports []Report) error {
         .      110ms    937:	sort.Slice(reports, func(i, j int) bool { return strings.Compare(reports[i].SoldAt, reports[j].SoldAt) < 0 })
         .          .    938:
         .          .    939:	body := bytes.NewBufferString("reservation_id,event_id,rank,num,price,user_id,sold_at,canceled_at\n")
         .          .    940:	for _, v := range reports {
         .      280ms    941:		body.WriteString(fmt.Sprintf("%d,%d,%s,%d,%d,%d,%s,%s\n",
         .       20ms    942:			v.ReservationID, v.EventID, v.Rank, v.Num, v.Price, v.UserID, v.SoldAt, v.CanceledAt))
         .          .    943:	}
         .          .    944:
         .          .    945:	c.Response().Header().Set("Content-Type", `text/csv; charset=UTF-8`)
         .          .    946:	c.Response().Header().Set("Content-Disposition", `attachment; filename="report.csv"`)
         .          .    947:	_, err := io.Copy(c.Response(), body)
ROUTINE ======================== main.renderReportCSV.func1 in /home/isucon/local/go/src/strings/compare.go
      10ms       60ms (flat, cum)  0.58% of Total
         .          .     16:	// using strings.Compare. Basically no one should use strings.Compare.
         .          .     17:	// As the comment above says, it is here only for symmetry with package bytes.
         .          .     18:	// If performance is important, the compiler should be changed to recognize
         .          .     19:	// the pattern so that all code doing three-way comparisons, not just code
         .          .     20:	// using strings.Compare, can benefit.
         .       30ms     21:	if a == b {
         .          .     22:		return 0
         .          .     23:	}
      10ms       30ms     24:	if a < b {
         .          .     25:		return -1
         .          .     26:	}
         .          .     27:	return +1
         .          .     28:}
ROUTINE ======================== main.renderReportCSV.func1 in /home/isucon/torb/webapp/go/src/torb/app.go
      20ms       20ms (flat, cum)  0.19% of Total
         .          .    932:	CanceledAt    string
         .          .    933:	Price         int64
         .          .    934:}
         .          .    935:
         .          .    936:func renderReportCSV(c echo.Context, reports []Report) error {
      20ms       20ms    937:	sort.Slice(reports, func(i, j int) bool { return strings.Compare(reports[i].SoldAt, reports[j].SoldAt) < 0 })
         .          .    938:
         .          .    939:	body := bytes.NewBufferString("reservation_id,event_id,rank,num,price,user_id,sold_at,canceled_at\n")
         .          .    940:	for _, v := range reports {
         .          .    941:		body.WriteString(fmt.Sprintf("%d,%d,%s,%d,%d,%d,%s,%s\n",
         .          .    942:			v.ReservationID, v.EventID, v.Rank, v.Num, v.Price, v.UserID, v.SoldAt, v.CanceledAt))
(pprof) 
```

main.getEventに絞る
```shell
(pprof) list main.getEvent
Total: 10.37s
ROUTINE ======================== main.getEvent in /home/isucon/torb/webapp/go/src/torb/app.go
      50ms      6.17s (flat, cum) 59.50% of Total
         .          .    239:	if err != nil {
         .          .    240:		return nil, err
         .          .    241:	}
         .          .    242:	defer rows.Close()
         .          .    243:
      10ms      140ms    244:	for rows.Next() {
         .       30ms    245:		var sheet Sheet
         .      140ms    246:		if err := rows.Scan(&sheet.ID, &sheet.Rank, &sheet.Num, &sheet.Price); err != nil {
         .          .    247:			return nil, err
         .          .    248:		}
         .          .    249:		event.Sheets[sheet.Rank].Price = event.Price + sheet.Price
         .          .    250:		event.Total++
         .       10ms    251:		event.Sheets[sheet.Rank].Total++
         .          .    252:
         .       70ms    253:		var reservation Reservation
      10ms      5.72s    254:		err := db.QueryRow("SELECT * FROM reservations WHERE event_id = ? AND sheet_id = ? AND canceled_at IS NULL GROUP BY event_id, sheet_id HAVING reserved_at = MIN(reserved_at)", event.ID, sheet.ID).Scan(&reservation.ID, &reservation.EventID, &reservation.SheetID, &reservation.UserID, &reservation.ReservedAt, &reservation.CanceledAt)
         .          .    255:		if err == nil {
         .          .    256:			sheet.Mine = reservation.UserID == loginUserID
         .          .    257:			sheet.Reserved = true
         .          .    258:			sheet.ReservedAtUnix = reservation.ReservedAt.Unix()
         .          .    259:		} else if err == sql.ErrNoRows {
         .          .    260:			event.Remains++
      10ms       20ms    261:			event.Sheets[sheet.Rank].Remains++
         .          .    262:		} else {
         .          .    263:			return nil, err
         .          .    264:		}
         .          .    265:
      20ms       40ms    266:		event.Sheets[sheet.Rank].Detail = append(event.Sheets[sheet.Rank].Detail, &sheet)
         .          .    267:	}
         .          .    268:
         .          .    269:	return &event, nil
         .          .    270:}
         .          .    271:
ROUTINE ======================== main.getEvents in /home/isucon/torb/webapp/go/src/torb/app.go
         0      3.67s (flat, cum) 35.39% of Total
         .          .    191:	if err != nil {
         .          .    192:		return nil, err
         .          .    193:	}
         .          .    194:	defer tx.Commit()
         .          .    195:
         .       10ms    196:	rows, err := tx.Query("SELECT * FROM events ORDER BY id ASC")
         .          .    197:	if err != nil {
         .          .    198:		return nil, err
         .          .    199:	}
         .          .    200:	defer rows.Close()
         .          .    201:
         .          .    202:	var events []*Event
         .          .    203:	for rows.Next() {
         .          .    204:		var event Event
         .          .    205:		if err := rows.Scan(&event.ID, &event.Title, &event.PublicFg, &event.ClosedFg, &event.Price); err != nil {
         .          .    206:			return nil, err
         .          .    207:		}
         .          .    208:		if !all && !event.PublicFg {
         .          .    209:			continue
         .          .    210:		}
         .          .    211:		events = append(events, &event)
         .          .    212:	}
         .          .    213:	for i, v := range events {
         .      3.66s    214:		event, err := getEvent(v.ID, -1)
         .          .    215:		if err != nil {
         .          .    216:			return nil, err
         .          .    217:		}
         .          .    218:		for k := range event.Sheets {
         .          .    219:			event.Sheets[k].Detail = nil
(pprof) 
```

