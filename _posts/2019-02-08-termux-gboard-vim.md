---

layout: post

title: termux下gboard中文输入法在vim中的应用

tags:

- 电脑技术

---

在termux中用gboard输入法输入中文，实在是有点麻烦。通过多次搜索尝试，终于找到了窍门：

左划长按keyboard会出现快捷键条，把它往左划就能输中文了

不过，就是在左划时，手指最好放在end键附近，否则光标总会跑到别的地方去，徒增烦扰。

另外，为了解决vim中出现中文乱码问题，最好在.vimrc中增加如下设置：

```
cd ~
vim .vimrc
set encoding=utf-8
set fileencodings=ucs-bom,utf-8,cp936,gb18030
set termencoding=utf-8
set expandtab
set ts=4
set shiftwidth=4
set nu
syntax on

if has('mouse')
set mouse-=a
endif

```

如此，就可以解决中文乱码问题。
