---
title: Pingpingping
date: 2026-01-28 12:00:00
tags:
  - 题解
  - RCE
  - 命令注入
---

这里Ping_ip.exe可以get传参执行命令，但是_会因为php解析把 .也变成_

所以这里用[代替_,直接?Ping[ip.exe=127.0.0.1;cat /f*得到flag


![Pingpingping_8f4aef18](/images/writeups/Pingpingping_8f4aef18.png)
