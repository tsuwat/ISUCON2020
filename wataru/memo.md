#ISUCON

[ISUCON入賞者のブログ](https://beatsync.net/main/log20171023.html)

##環境チェック
与えられた環境のリソースと性能を確認する
* Diskの性能確認http://naoberry.com/tech/hdparm/
** hdparm -t /dev/sda1 とかとか。ディスクの読み出し/書きだし速度を遅ければ極力メモリ上で処理できるようにする。
* メモリの性能確認
** cat /proc/meminfo
* CPUの性能確認
** cat /proc/cpuinfo
* その為　https://qiita.com/aosho235/items/c4d6995743dd1dac16e1
** vmstat -m 2 これで全体の性能を先にまるっと把握するのもあり

 
