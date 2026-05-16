---
title: PseudoProtocols
date: 2026-02-06 12:00:00
tags:
  - 题解
---

`题目问我们能找到hint.php这里发现url中有一个?wllm=,尝试读取php://filter/read=convert.base64-encode/resource=hint.php，解码后发现让我们去/test2222222222222.php，打开发现要得到一个a文件内容是I want flag，这里用data协议a=data://text/plain,I want flag成功得到flag`

``