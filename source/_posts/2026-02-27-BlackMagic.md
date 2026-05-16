---
title: BlackMagic
date: 2026-02-27 12:00:00
tags:
  - 题解
---

这道题查看源码发现$strTmp == $strContent时可以得到flag


![BlackMagic_ec9b716a](/images/writeups/BlackMagic_ec9b716a.png)


$strContent 是由 trim($strFlag, $strCharList);得到的这里写一段代码直接算出$strContent，再传个相同值的$strTmp 


![BlackMagic_aa876d2a](/images/writeups/BlackMagic_aa876d2a.png)

![BlackMagic_61f068b5](/images/writeups/BlackMagic_61f068b5.png)


输入?strTmp=%09xxxxx...xxxxx%09得到flag


![BlackMagic_52f70ea3](/images/writeups/BlackMagic_52f70ea3.png)
