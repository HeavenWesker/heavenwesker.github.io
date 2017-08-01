title: "关于Ubuntu的Unity以及状态栏消失的解决办法"
id: 73
date: 2013-03-03 06:35:50
tags: 
- ubuntu
- 日常维护
categories: 
- Ubuntu
---

今日小编的Ubuntu因为想试一下amd的开源驱动谁知换驱动后Unity和status bar直接私奔了，这俩货。。。

无奈，首先：

    sudo unity --reset
数分钟后卡在某一步上只能&lt;C-c&gt;了然后重启lightdm：

    sudo service lightdm restart
如果你的Ubuntu版本比较底如Ubuntu9及更早版本就应该尝试重启gdm而非lightdm：

    sudo service gdm restart
我的重启后无效。

然后第二次尝试，清除Unity及compiz的配置文件希望有用：
    
    rm -rf ~/.compiz* ~/.config/compiz* ~/.gconf/apps/compiz* ~/.cache/compiz* ~/.config/dconf ~/.cache/dconf ~/.cache/unity*
悲剧的是重启后依然无效于是我想干脆直接重装unity和compiz：

    sudo apt-get remove compiz 
    sudo apt-get remove unity 
    sudo apt-get install compiz 
    sudo apt-get install unity
ok，这次好了Unity和status bar都回来了，只是自定义的快捷键失效了，不过点几下就好了呀，打完手工～
