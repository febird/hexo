---
title: Mysql utf8 and utf8mb4
date: 2018-04-27 15:11:32
tags:
---

utf8mb4和utf8区别如下：
MySQL在5.5.3之后增加了这个utf8mb4的编码，mb4就是most bytes 4的意思，专门用来兼容四字节的unicode。好在utf8mb4是utf8的超集，除了将编码改为utf8mb4外不需要做其他转换。当然，为了节省空间，一般情况下使用utf8也就够了。