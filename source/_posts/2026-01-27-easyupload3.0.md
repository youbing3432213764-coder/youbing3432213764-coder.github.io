---
title: easyupload3.0
date: 2026-01-27 12:00:00
tags:
  - 题解
  - 文件上传
---

这里抓包修改失败


![easyupload3.0_c1901345](/images/writeups/easyupload3.0_c1901345.png)


网页标签提醒我们试试和某些文件配合，发现服务器是服务器是Apache，尝试上传.htaccess进行绕过。先上传.htaccess

在传一句话木马（.jpg格式），上传成功用蚁剑连接找到flag


![easyupload3.0_fa6ef427](/images/writeups/easyupload3.0_fa6ef427.png)
