---
layout: post

title: linux下设置短命令

tags:

- 电脑技术

---

　　在LINUX中，有很多常用的命令，常用的命令我们可以熟练的记忆，但是对于不经常使用的命令恐怕是需要翻阅手册了，但是我们可以简化这些命令的输入来达到简便记忆的效果。 

　　这里以termux下的BASH为例： 

　　编辑
```
/data/data/com.termux/files/usr/etc/bash.bashrc
```
这个文件（所有使用这个SHELL的用户都可以享受到便利,如果没有ROOT权限，则编辑你自己目录下的.bashrc文件，区别在于只有你自己可以使用下面定义的别名） 

　　在最后加入这一段： 

```
　　alias l="ls --color -l" 
　　alias lm="ls --color -l | more" 
　　alias la="ls --color -l -a" 
```

　　这样，我们就可以单独使用“l”来列出长目录了。而使用“lm”则可以分屏列出目录，至于“la”则同时列出隐含文件。 

