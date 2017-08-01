title: "MarkDown editor on Linux"
id: 45
date: 2014-03-17 20:34:45
tags: 
- markdown
categories: 
- editor
---

从Google找了很久终于找到了一个我能够看顺眼的MarkDown编辑器，美观大方，简洁不失优雅，必须点赞啦～<br>
先上图啦<br>
官网：http://pad.haroopress.com/user.html<br>
不过呢，就是在Ubuntu下依赖关系没有理顺，需要自己手动处理一下：<br>
* * *
##for Debian/Ubuntu

`wget https://dl.dropbox.com/s/2km44jkax2lsarf/haroopad-v0.11.1_amd64.deb`

`sudo dpkg -i haroopad-v0.11.1_amd64.deb`

`sudo apt-get install libudev1 libudev-dev -y`

`sudo ln -sf /lib/x86_64-linux-gnu/libudev.so.1 /lib/x86_64-linux-gnu/libudev.so.0`


{% asset_img Haroopad.png Haroopad %}

