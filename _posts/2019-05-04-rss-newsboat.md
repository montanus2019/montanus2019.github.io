---
layout: post
title: 重归rss
tags:
- 电脑技术
---
字符界面下，termux中内置可安装的rss的阅读器，只有newsboat可用。

## newsboat的安装

termux下只需要输入

```
pkg install newsboat
```

配置newsboat，在~/.newsboat目录下创建并编辑urls文件，将rss网址逐行输入即可。

如有rss源文件的话，也可以用命令行``` newsboat -i *.opml```的形式导入opml文件

## 一个好用的查找rss源的网址

https://rsshub.app


