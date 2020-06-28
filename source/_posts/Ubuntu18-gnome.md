---
title: Ubuntu 18 gnome 桌面环境很卡 xfce4 安装
date:  2019-05-25
---
## 判断系统是gnome，kde还是unity？

```
$ update-alternatives --display x-session-manager
```

> x-session-manager - auto mode 
> link best version is /usr/bin/gnome-session
>  link currently points to /usr/bin/gnome-session
>  link x-session-manager is /usr/bin/x-session-manager
>  slave x-session-manager.1.gz is /usr/share/man/man1/x-session-manager.1.gz
>  /usr/bin/gnome-session - priority 50
>  slave x-session-manager.1.gz: /usr/share/man/man1/gnome-session.1.gz
>  /usr/bin/startxfce4 - priority 50
>  slave x-session-manager.1.gz: /usr/share/man/man1/startxfce4.1.gz
>  /usr/bin/xfce4-session - priority 40 slave x-session-manager.1.gz: /usr/share/man/man1/xfce4-session.1.gz 
> There are 3 choices for the alternative x-session-manager (providing /usr/bin/x-session-manager).

##  修改启动顺序

方法一：
```
$ update-alternatives --config x-session-manager
```
> Selection Path Priority Status 
> * 0 /usr/bin/gnome-session 50 auto mode 
>   1 /usr/bin/gnome-session 50 manual mode 
>   2 /usr/bin/startxfce4 50 manual mode 
>  3 /usr/bin/xfce4-session 40 manual mode 
> Press <enter> to keep the current choice[*], or type selection number:

输入2，检查执行结果：

>  Selection Path Priority Status 
> 0 /usr/bin/gnome-session 50 auto mode 
> 1 /usr/bin/gnome-session 50 manual mode 
> * 2 /usr/bin/startxfce4 50 manual mode 
> 3 /usr/bin/xfce4-session 40 manual mode 
> Press <enter> to keep the current choice[*], or type selection number:


重新启动，即可。
方法二：
在重启后的登录界面，点击登录旁边的设置按钮，选择xfce4桌面环境，即可。


