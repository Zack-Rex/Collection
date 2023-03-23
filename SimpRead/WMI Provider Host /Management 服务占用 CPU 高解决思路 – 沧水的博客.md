> 本文由 [简悦 SimpRead](http://ksria.com/simpread/) 转码， 原文地址 [cangshui.net](https://cangshui.net/4327.html)

> 如果你的电脑出现 WMI Provider Host 这个进程和 Windows Management Ibstrumentation 服务 CPU 占用高，恭喜你，你可能是最新的雷蛇驱动的受害者 如何判断？......

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
