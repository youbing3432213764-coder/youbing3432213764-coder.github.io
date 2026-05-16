---
title: Ping Ping Ping
date: 2026-02-02 12:00:00
tags:
  - 题解
  - RCE
  - 命令注入
---

这里提示可以执行命令，尝试输入127.0.0.1;ls,发现flag.php和index.php,直接cat flag.php

发现空格被禁止了flag也被禁止了，127.0.0.1;cat$IFS$9`ls`这里先执行ls再执行cat发现index.php的内容显示在下面了应该是执行成功，没看到flag打开源码查看发现flag


![Ping-Ping-Ping_b1712aa5](/images/writeups/Ping-Ping-Ping_b1712aa5.png)
