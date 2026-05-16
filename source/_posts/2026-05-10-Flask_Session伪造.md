---
title: Flask_Session伪造
date: 2026-05-10 12:00:00
tags:
  - 题解
  - Session
  - Flask
---

题目显示可以读取网页


![Flask_Session伪造_35153660](/images/writeups/Flask_Session伪造_35153660.png)


点击后会跳转百度，查看源码发现这里有一个url参数


![Flask_Session伪造_b0f33032](/images/writeups/Flask_Session伪造_b0f33032.png)


用file协议可以读取文件


![Flask_Session伪造_a47c83c8](/images/writeups/Flask_Session伪造_a47c83c8.png)


题目叫Flask_Session伪造,需要secret_key，一般在app.py中


![Flask_Session伪造_1917bde4](/images/writeups/Flask_Session伪造_1917bde4.png)


这里需要admin签名的cookie才能访问/flag，所以需要先得到mac地址，然后算secret_key，再去伪造{'username':'admin'} 的签名 Cookie，最后替换cookie访问/flag。因为可以读取文件，先看看能不能直接读网卡信息得到mac地址。

Payload：/read?url=file:///sys/class/net/eth0/address


![Flask_Session伪造_a8f6fd1e](/images/writeups/Flask_Session伪造_a8f6fd1e.png)
用脚本计算secret_key


![Flask_Session伪造_022c0a7c](/images/writeups/Flask_Session伪造_022c0a7c.png)



![Flask_Session伪造_99a6de20](/images/writeups/Flask_Session伪造_99a6de20.png)


得到secret_key为0.5088633266314257，用flask-session-cookie-manager伪造session


![Flask_Session伪造_8db25bcb](/images/writeups/Flask_Session伪造_8db25bcb.png)



![Flask_Session伪造_259c58df](/images/writeups/Flask_Session伪造_259c58df.png)


eyJ1c2VybmFtZSI6ImFkbWluIn0.af_3Mw.CpCI19wit_JWsNvwVA5W5vmcaZw 

修改cookie访问/flag获得flag


![Flask_Session伪造_4a2b7b59](/images/writeups/Flask_Session伪造_4a2b7b59.png)


CTF{flask_session_is_secure}