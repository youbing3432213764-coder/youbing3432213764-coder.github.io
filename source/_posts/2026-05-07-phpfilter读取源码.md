---
title: phpfilter读取源码
date: 2026-05-07 12:00:00
tags:
  - 题解
  - PHP
  - 代码审计
---

题目名字叫php://filter读取源码，猜测可能需要php伪协议读取文件源码，尝试输入一个路径看看什么情况


![phpfilter读取源码_3ba6824c](/images/writeups/phpfilter读取源码_3ba6824c.png)


被禁用了，查看一下当前页面的源码看看什么情况

php://filter/convert.base64-encode/resource=index.php


![phpfilter读取源码_ec9eafa6](/images/writeups/phpfilter读取源码_ec9eafa6.png)


Base64解码后发现这里包含了一个db.php文件


![phpfilter读取源码_4e64daa3](/images/writeups/phpfilter读取源码_4e64daa3.png)


再用同样的方法查看一下db.php文件中有什么


![phpfilter读取源码_1b6f2561](/images/writeups/phpfilter读取源码_1b6f2561.png)


Base64解码后发现flag


![phpfilter读取源码_2a444633](/images/writeups/phpfilter读取源码_2a444633.png)


CTF{3ecret_passw0rd_here}