
---

--- 

~~梦里都听到你说我懒，可是你能拿我怎么办？~~
##### 简单说明
本文抛开翻墙这一基本素质以外，开始写一些比较简单的记录方法。也希望如果有个学弟或者是学妹加入，我是说那种喜欢研究的，恩。。。至于大学以后嘛。。也是可以慢慢研究哒 ，哈哈哈哈哈，欢迎加入我们单身汪一族。emmmm我是认真的。提前一年开始沉淀，可不是什么坏事；emmm好吧 ，本届的也不慌，那么开始正文。
##### 前缀语法markdown
电脑什么的人不常有，but手机常用，且人常用之，所以下面写一下如何用手机app和githubPage 制作一个简单blog，语法首推markrown，如果语法不是很好，建议参考[简书上的简单的markdown语法入门](https://www.jianshu.com/p/8375e0d5a412)

##### 安卓软件准备

- markdownx 在支持markdown语法的基础上，顶部可以使用图形化加入 常见markrown标记也是对新人和懒人非常友好的。
- termux，不需要root的终端shell，比较大众化的终端。
##### github准备工作
在GitHub上注册一个帐号，然后新建一个项目，名为countname.github.io便会自动被认为是一个github Page页
##### 开始搭建

- 打开termux（第一次连接可能需要翻墙）安装git和jekyll
输入下列命令，并回车，新手如果不会请分开执行，如pkg update
pkg jnstall libffi-dev


```
pkg update && pkg install libffi-dev clang ruby  ruby-dev make 
gem install jekyll
pkg install git
```

- 打开markdown x，写下这篇文章，记得遵循jekyll 命名原则， 例如：2018-01-31-jekyll.md
-再次打开termux，输入 

```
git clone https://gitub.com/zhogjiane/zhogjiane.github.io.git

```

- 将我的博客复制到本地去掉自己不喜欢的js css 等描述文件就好，将yml中关于我的描述，全部改成自己喜欢的或者是你的描述即可。这里涉及到另一些android app的使用本篇不做过多叙述。
好看的模板也可以在 [jekyll模板选择](http://jekyllthemes.org)选择自己喜欢的主题风格。

- 修改完成后 
使用git命令添加到自己的文件夹中
git命令：

```
git add .      #添加文件夹
git commit -m"描述信息"    #描述文件
git push origin master         # 提交文件 

```
-------

如果git有错误信息，请尝试重新初始化配置，或者再次检查git config user.name  和git config user.email 
可能涉及 linux常规操作命令：

```
rm -rf * #删除所有文件
mv filename filename2#重命名
mv filepath/filename filepath2/filename#移动文件

```
