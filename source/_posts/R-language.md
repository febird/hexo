---
title: R语言画三角函数图形
date: 2017-07-22 16:39:44
tags:
---

最近看到个数学题，想画个图形，想起Matlab，但是安装包太庞大，太重量级，想到了R语言，这是个用于统计和绘图的编程语言，试了一下，很小巧，65MB，用起来很方便。

比如要画一个 y=sin(2x)+cos(3x)的曲线，两行代码：
```r
x <- seq(-2*pi,2*pi,length.out=1000)
plot(x,sin(2*x)+cos(3*x),type='l')
```
执行如图：
![R简单画图](https://febird.github.io/images/R.PNG)