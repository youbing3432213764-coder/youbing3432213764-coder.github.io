---
title: PolarShop
date: 2026-04-09 12:00:00
tags:
  - 题解
---

打开题目发现有很多商品要积分换


![PolarShop_63edd2f5](/images/writeups/PolarShop_63edd2f5.png)


修改源码尝试从前端修改积分


![PolarShop_77250e6c](/images/writeups/PolarShop_77250e6c.png)


将所有能换的换完得到一个文件暂时不知道作用，店主的秘密无法兑换查看前端代码也没找到办法


![PolarShop_087c5df0](/images/writeups/PolarShop_087c5df0.png)


尝试扫目录，发现admin.php


![PolarShop_35c013ba](/images/writeups/PolarShop_35c013ba.png)


查看admin.php出现管理员界面


![PolarShop_963475b5](/images/writeups/PolarShop_963475b5.png)


猜测刚刚的txt文件可能是密码字典抓包爆破一下


![PolarShop_5c14898a](/images/writeups/PolarShop_5c14898a.png)


成功得到密码登录到后台


![PolarShop_516a085f](/images/writeups/PolarShop_516a085f.png)


查看店主的密码发现不让查看，发现cookie中有个user属性修改为Squirtle 看看能不能查看密码


![PolarShop_e3893288](/images/writeups/PolarShop_e3893288.png)


修改后请求得到flag


![PolarShop_2d24b743](/images/writeups/PolarShop_2d24b743.png)
