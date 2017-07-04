---
title: Hexo不能生成Post
date: 2017-06-21 21:35:15
tags: Hexo
---

很早之前了解了一下hexo，但之前一直都没有部署到Github，这两天心血来潮，而且Github作为公司内网为数不多的“合法网站”，资源可以好好利用一些。
我使用Hexo的思路很简单：
1. hexo 这个 repo 作为原始资料存放目录，通过git管理，发布到github，通过gitignore排除public。
2. febird.github.io 这个repo 作为hexo的发布目录也就是上面的public，也通过git管理，发布到github。
3. 每次通过hexo new 一个post，然后hexo g生成静态内容，然后通过commit并push到public

但是昨天搞好了的hexo，可以正常生成和发布，今天怎么都生成不了静态内容，很是奇怪，hexo g 也不会报任何错误，但总是 0 Files updated.
打开debug选项也是没有报任何错误，晚上一步小心输入了一下npm list，惊奇的发现少了依赖：
``` bash
npm ERR! missing: hexo-generator-archive@^0.1.4, required by hexo-site@0.0.0
npm ERR! missing: hexo-generator-category@^0.1.3, required by hexo-site@0.0.0
npm ERR! missing: hexo-generator-index@^0.2.0, required by hexo-site@0.0.0
npm ERR! missing: hexo-generator-tag@^0.2.0, required by hexo-site@0.0.0
npm ERR! missing: hexo-renderer-ejs@^0.2.0, required by hexo-site@0.0.0
npm ERR! missing: hexo-renderer-marked@^0.2.10, required by hexo-site@0.0.0
npm ERR! missing: hexo-renderer-stylus@^0.3.1, required by hexo-site@0.0.0
```
难道是hexo被我后来卸载又安装啥东西搞坏了？有可能，安装完成试试看：
``` bash
npm install hexo-generator-archive hexo-generator-category hexo-generator-index hexo-generator-tag hexo-renderer-ejs hexo-renderer-marked hexo-renderer-stylus --save
npm WARN prefer global marked@0.3.6 should be installed with -g
hexo-site@0.0.0 E:\MyDoc\GitHub\hexo
``` 
装完了果然OK。