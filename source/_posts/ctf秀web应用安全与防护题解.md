---
title: ctfshow web应用安全与防护题解
date: 2026-03-16 23:06:00
tags: 题解
---

## Base64编码隐藏

打开题目f12查看源码发现密码被base64加密

![1773670223912](/images/ctfshow/1773670223912.png)

解码得到密码

![1773670666647](/images/ctfshow/1773670666647.png)

登录得到flag

![1773670740030](/images/ctfshow/1773670740030.png)

## HTTP头注入

f12查看源码发现密码被base64加密

![1773670223912](/images/ctfshow/1773670223912.png)

解码得到密码

![1773670666647](/images/ctfshow/1773670666647.png)

登录提示只能ctf-show-brower登录

![1773671083716](/images/ctfshow/1773671083716.png)

这里抓包修改（靶场默认开启https，删除s切换回http再抓包）

![1773671245832](/images/ctfshow/1773671245832.png)

发送请求包得到flag

![1773671327314](/images/ctfshow/1773671327314.png)

## Base64多层嵌套解码

这里步骤跟“HTTP头注入”一样，只是中间的解码的步骤复杂了一些

第1步逆向：Base64解码 text atob("SXpVRlF4TTFVelJtdFNSazB3VTJ4U1UwNXFSWGRVVlZrOWNWYzU=")

第2步逆向：这一步是 btoa('aB3' + encoded + 'qW9').substr(2) 对第1步结果Base64解码 得到完整字符串，前面补回2个字符 去掉开头的"aB3"和结尾的"qW9"

第3步逆向：这一步是 btoa(encoded.split('').reverse().join('')) 对第2步结果Base64解码 将字符串反转 

第4步逆向：这一步是 btoa(encoded + 'xH7jK').slice(3) 对第3步结果Base64解码 开头补回3个字符 去掉结尾的"xH7jK"

第5步逆向：最后Base64解码，得到原始密码