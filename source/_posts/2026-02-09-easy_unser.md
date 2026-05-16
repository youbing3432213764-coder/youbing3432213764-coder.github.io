---
title: easy_unser
date: 2026-02-09 12:00:00
tags:
  - 题解
  - 反序列化
---

这里要绕过__wakeup()修改$want而且不被is_file()检测到，保证 $todonothing !== $want，还要注意私有化属性

`构造payload：O:4:"body":3:{s:10:"\x00body\x00want";s:30:"php://filter/resource=f14g.php";s:17:"\x00body\x00todonothing";s:1:"1";}编码后输入得到flag`


![easy_unser_73bff43a](/images/writeups/easy_unser_73bff43a.png)
