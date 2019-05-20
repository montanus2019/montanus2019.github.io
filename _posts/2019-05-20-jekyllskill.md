---
layout: post

title: jekyll 小窍门

tags:

- 电脑技术

---

转自

https://blog.csdn.net/ds19991999/article/details/81293467

为博客添加各种功能

效果见：ds19991999的博客

1.关于Jekyll本身插件的安装

一共三种方式: 
* 在根目录下新建_plugins文件夹, 然后把对应的*.rb插件文件放进去就行了; 
* 在_config.yml文件中增加一个gems关键字, 然后把要引用的插件用数组形式存储其中即可; 
* 在Gemfile中添加相关的插件;

三种方法都可以, 甚至完全可以同时使用~

2.用kramdown自动生成目录树

启用kramdown，即在_config.yml中添加```markdown: kramdown```这一行

在md文章中需要插入目录的地方添加：

```
* 目录 
{:toc}

```
第一行必须加！



本文共{{ content | strip_html | strip_newlines | split: "" | size }}字。

