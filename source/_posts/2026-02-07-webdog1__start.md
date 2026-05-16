---
title: webdog1__start
date: 2026-02-07 12:00:00
tags:
  - 题解
---

发现源码中的注释让我们传一个web，web的MD5值和他本来的值一样这里传一个0e215962017然后进入了start.php，注释中让我们去看robots协议，打开robots.txt,发现是乱码修复编码后告诉我们f14g.php,进入f14g.php告诉我们这里是假的但是找了别的地方没有找到线索查看网络时发现让我们去F1l1l1l1l1lag.php，打开发现源代码这里不让用flag和空格构造一个绕过的payload：system("nl%09/*");成功得到flag


![webdog1__start_d9f92a51](/images/writeups/webdog1__start_d9f92a51.png)
