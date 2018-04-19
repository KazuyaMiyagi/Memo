# timezone

see https://docs.aws.amazon.com/ja_jp/AWSEC2/latest/UserGuide/set-time.html

```
$ sudo ln -sf /usr/share/zoneinfo/Asia/Tokyo /etc/localtime

$ ls -l /etc/localtime
lrwxrwxrwx 1 root root 30 Mar 29 16:08 /etc/localtime -> /usr/share/zoneinfo/Asia/Tokyo

$ date
Thu Mar 29 16:09:00 JST 2018

$ sudo vim /etc/sysconfig/clock
$ cat /etc/sysconfig/clock
ZONE="Asia/Tokyo"
UTC=true
```
