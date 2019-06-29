---
title: "Github Boost"
date: 2019-06-29T12:08:54+08:00
draft: false
toc: false
images:
tags: 
  - hack
  - network
---

> GayHub 又卡了...
>
> 我 Clone 一个代码难道要挂到明天早上？

## GitHub 访问速度究竟是谁的锅？

实践证明，GFW 并没有对 GitHub 做任何限制，至少现在是这样。根据我的实际观察，问题出在 DNS 上。在中国，默认的解析是这样的：

```
; <<>> DiG 9.10.4-P5 <<>> @8.8.8.8 github.com
; (1 server found)
;; global options: +cmd
;; Got answer:
;; ->>HEADER<<- opcode: QUERY, status: NOERROR, id: 60271
;; flags: qr rd ra; QUERY: 1, ANSWER: 3, AUTHORITY: 0, ADDITIONAL: 1

;; OPT PSEUDOSECTION:
; EDNS: version: 0, flags:; udp: 512
;; QUESTION SECTION:
;github.com.                    IN      A

;; ANSWER SECTION:
github.com.             59      IN      A       52.74.223.119
github.com.             59      IN      A       13.229.188.59
github.com.             59      IN      A       13.250.177.223

;; Query time: 69 msec
;; SERVER: 8.8.8.8#53(8.8.8.8)
;; WHEN: Mon Feb 04 23:55:07 CST 2019
;; MSG SIZE  rcvd: 87
```

在世界的其他地方，结果是这样的：

```
; <<>> DiG 9.10.3-P4-Debian <<>> @8.8.8.8 github.com
; (1 server found)
;; global options: +cmd
;; Got answer:
;; ->>HEADER<<- opcode: QUERY, status: NOERROR, id: 58526
;; flags: qr rd ra; QUERY: 1, ANSWER: 2, AUTHORITY: 0, ADDITIONAL: 1

;; OPT PSEUDOSECTION:
; EDNS: version: 0, flags:; udp: 512
;; QUESTION SECTION:
;github.com.                    IN      A

;; ANSWER SECTION:
github.com.             59      IN      A       192.30.253.112
github.com.             59      IN      A       192.30.253.113

;; Query time: 29 msec
;; SERVER: 8.8.8.8#53(8.8.8.8)
;; WHEN: Mon Feb 04 15:57:07 UTC 2019
;; MSG SIZE  rcvd: 71
```

这印证了一个真理：世界互联网分为两个部分...

## 解决方法

利用 hosts 文件，强行指定 GitHub IP。

```
192.30.255.113 github.com
```

Done.