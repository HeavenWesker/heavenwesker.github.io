title: "Ubuntu notify-osd 不支持 -t 标签的解决办法"
date: 2014-04-02 13:00:00
tags:
- ubutnu

categories:
- ubuntu

---
ubuntu 下默认的通知系统是notify-send + notify-osd 

notify-send 命令常用格式如下：

`notify-send -t <timeout> "title" "body"`

`<timeout>`是通知在屏幕驻留的时间，单位毫秒计,所以显然notify-send是支持调整时间的，可是事实上无论你的 `-t`标签后面跟多少这个时间都是不变的，而且我总是觉得这个时间太长了，完全没有实时性嘛，很不科学。但是这个问题事实上不怪notify-send是因为notify-osd直接忽略了`-t`标签！问题找到了，解决方案当然也有了啊，国外有开发者已经修复了这个BUG：

	sudo add-apt-repository ppa:leolik/leolik
	sudo apt-get update
	sudo apt-get upgrade
	sudo apt-get install libnotify-bin
	pkill notify-osd
    
这样就好了

如果你还想自定义通知的位置，颜色等等，可以使用这个工具NotifyOSDConfig

	sudo add-apt-repository ppa:amandeepgrewal/notifyosdconfig
	sudo apt-get update
	sudo apt-get install notifyosdconfig
    
然后

`notifyosdconfig`命令打开设置notify-osd如图所示：
![notifyosdconfig](https://aiwenhao.com/img/notifyosdconf.png)
自己慢慢调，总会调得很顺眼的
