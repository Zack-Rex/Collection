> 本文由 [简悦 SimpRead](http://ksria.com/simpread/) 转码， 原文地址 [cangshui.net](https://cangshui.net/4327.html)

> 如果你的电脑出现 WMI Provider Host 这个进程和 Windows Management Ibstrumentation 服务 CPU 占用高，恭喜你，你可能是最新的雷蛇驱动的受害者 如何判断？......

[![](https://cangshui.net/wp-content/uploads/2017/07/145-300x300.jpg)](https://cangshui.net/)

[

#### 沧水的博客

](https://cangshui.net/)

@

*   [生活随写](https://cangshui.net/class/note)
*   [资源分享](https://cangshui.net/class/share)
*   [网页制作](https://cangshui.net/class/html)
*   [VPS 购买](https://cangshui.net/class/vps)
*   [系统运维](https://cangshui.net/class/maintain)
*   [实用软件](https://cangshui.net/class/exe)
*   [游戏娱乐](https://cangshui.net/class/game)

发布于 2019 年 6 月 30 日 / [实用软件](https://cangshui.net/class/exe) / [6 条评论](https://cangshui.net/4327.html#comments)

![](https://cangshui.net/wp-content/uploads/2019/06/20190630113612.png)

如果你的电脑出现 WMI Provider Host 这个进程和 Windows Management Ibstrumentation 服务 CPU 占用高，恭喜你，你可能是最新的雷蛇驱动的受害者

如何判断？

运行输入 Eventvwr.msc ，启动事件查看器

![](https://cangshui.net/wp-content/uploads/2019/06/20190630113851.png)

逐步点开 【】应用程序和服务日志】——【Microsoft】——【Windows】——【WMI-Activity】，可以看到如下界面

![](https://cangshui.net/wp-content/uploads/2019/06/20190630114014.jpg)

ClientProcessId 处的 ID 就是进程 PID，找到它：

![](https://cangshui.net/wp-content/uploads/2019/06/20190630114139.jpg)

罪魁祸首雷蛇程序，我打开更新日志一看它更新了啥？？？

![](https://cangshui.net/wp-content/uploads/2019/06/20190630114226-1024x631.jpg)

我只能说雷蛇 NMSL， 我看日志是昨天自动装的驱动，自动运行而且默认开机自启动的，除非你自己设置里关掉，雷蛇挖矿这个玩意是谁想出来的，今晚 biss 熬

![](https://cangshui.net/wp-content/uploads/2019/06/453453453.jpg)

本文基于《[署名 - 非商业性使用 - 相同方式共享 4.0 国际 (CC BY-NC-SA 4.0)](https://creativecommons.org/licenses/by-nc-sa/4.0/deed.zh)》许可协议授权  
转载原创文章请注明，转载自： [沧水的博客](https://cangshui.net/ "沧水的博客") » [WMI Provider Host / Management 服务占用 CPU 高解决思路](https://cangshui.net/4327.html "WMI Provider Host / Management服务占用CPU高解决思路")

[❤打赏](https://shop.cangshui.net/product/8.html)

![](https://cangshui.net/wp-content/themes/Inspire/avatar/morengtouxiang.jpg)

1.  ![](https://secure.gravatar.com/avatar/21cbd085537bcc74bec62bbcfef9a8a7?s=42&d=mm&r=g)
    
    方法 [@TA](https://cangshui.net/4327.html?replytocom=1955#respond) (斗帝)
    
    2019-09-25 下午 1:45
    
    hgdgg
    
2.  ![](https://secure.gravatar.com/avatar/deff50574487addc7100644b48890564?s=42&d=mm&r=g)
    
    555 [@TA](https://cangshui.net/4327.html?replytocom=1949#respond) (斗帝)
    
    2019-09-22 下午 3:13
    
    测试
    
3.  ![](https://secure.gravatar.com/avatar/59c148395fa961a2f7cb48b2254bffa9?s=42&d=mm&r=g)
    
    latte [@TA](https://cangshui.net/4327.html?replytocom=1813#respond) (斗帝)
    
    2019-08-06 下午 5:13
    
    666
    
4.  ![](https://secure.gravatar.com/avatar/9f642762a3f0aa68b1b2c9fc2e4d18a8?s=42&d=mm&r=g)
    
    hhh [@TA](https://cangshui.net/4327.html?replytocom=1782#respond) (斗帝)
    
    2019-07-29 下午 1:54
    
    测试测试
    
5.  ![](https://secure.gravatar.com/avatar/bc08f04a0227c177c76066e7bcced8e2?s=42&d=mm&r=g)
    
    what fuck [@TA](https://cangshui.net/4327.html?replytocom=1735#respond) (斗帝)
    
    2019-07-16 上午 10:13
    
    雷蛇牛逼
    
6.  ![](https://secure.gravatar.com/avatar/de351edd86fe5383873fc915f9046c91?s=42&d=mm&r=g)
    
    By 小伟 [@TA](https://cangshui.net/4327.html?replytocom=1687#respond) (斗帝)
    
    2019-07-04 上午 9:41
    
    雷蛇这是要作大死？脑子进屎了吧？