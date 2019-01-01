#### Linux常用命令

#### 关于mv

* 移动文件

  ~~~bash
  mv file1 filepath/filepath       # 移动单个文件
  mv file1 file2 file3   filepath/filepath   # 移动多个文件到单个目录，注意目录唯一 
  mv file1 -t filepath1/filepath    file2 -t filepath2/filepath
  # 移动多个文件到多个文件夹，使用参数 -t 后接目录名字 
  mv file1 file2 file3 filepath/filepath #如果目录一致可省略写法
  ~~~

* 重命名 

  ~~~bash
  mv file1 file2 # 将file1重命名为file2
  # 如果当前目录下也有命名为file2时，会进行覆盖操作。
  mv file1 filepath/file2 #在上一步的基础上还会移动文件。

  ~~~

  #### 关于批量操作

* 批量操作

  ~~~bash

  # 下面两个例子：
  # 利用*通配符将所有small 结尾的文件 重命名为 large 结尾的文件。
  # 使用zsh的例子 ：
  cat /etc/shells				# 看看 安装了哪些shell 是否安装过zsh
  brew isntall zsh			# 没有安装的话，以mac为例安装zsh
  autoload -U zmv 			# 初始化载入，启动zmv工具
  zmv 'image_(*)_small.png' 'image_$1_large.png'
  chsh -s /bin/bash           # 如果要换回bash的话
  # bash正则表达例子：
  rename "s/small/large/" image_*.png
  #关于两种方法 来说zsh似乎更长一些但是 zsh的功能强大，易于理解
  # bash 正则表达学好了 ， 利器。


  ~~~

  ​