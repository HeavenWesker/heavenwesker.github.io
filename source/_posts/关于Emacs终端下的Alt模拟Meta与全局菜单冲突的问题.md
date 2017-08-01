title: "关于Emacs终端下的Alt模拟Meta与全局菜单冲突的问题"
id: 137
date: 2013-12-11 11:37:28
tags: 
- Develop
- Emacs
categories: 
- Develop
---

以前都是用的VIM后来觉得另一个编辑器也应该用一下，毕竟这个世界就只有两个编辑器，不多嘛，o(∩∩)o...哈哈～抱着尝试的态度打开了emacs感觉很好，不过按键冲突总是让我很不爽M-v这个就是啦，在现代键盘上并没有Meta键，难道我要去买一个MIT的键盘！！？？虽然可以用ESC或Alt键来模拟可是这样会导致其他问题，ESC的问题在于ESC不能连按，理想情况下连按两次 Meta-v只应该需要3次按键，因为Meta键不应该放开。用ESC的时候这个就不成立了，必须放开ESC。。。太反人类了。那就换Alt如何无奈Alt会和系统全局此单冲突，导致Alt-v打开终端的View菜单，着实逆天。要不就用图形界面的Emacs可是真的不喜欢啊（一个字，丑 爆了）！如果能够禁用terminal的Alt键就好了，后来Google之发现gconf-editor真的可以搞定这个问题！如下：

    gconf-editor

依次找到这个：

    /apps/gnome-terminal/globle/use_mnemonics disable掉（就是取消勾勾）

然后世界一下就美好了～哦哦～
