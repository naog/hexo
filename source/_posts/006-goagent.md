title: 用GoAgent撸一个每天10G流量的科学上网利器
date: 2014-12-10
categories: 善用佳软
tags: GoAgent
permalink: 6
---

GoAgent是一个基于Google Appengine的代理工具，通过这个神器，可以更加自由的使用互联网。下面一起来搭建专属的科学上网利器吧。

既然是专属的利器，首先需要申请一批自己的appid,登录[Google App Engine](https://appengine.google.com/)(如果没有Google帐号迅速注册一个先)创建一个GAE应用，一个账户可以创建10个应用，每个应用每天1G流量，如果你整天都挂在网上，我建议你一次创建10个应用，如:goa1、goa2……，然后记住这些appid。

首先需要从GoAgent的主页<https://github.com/goagent/goagent>下载最新版本，修改 local\proxy.ini 中的 [gae] 下的 appid = 你的appid(多appid请用|隔开)。运行 uploader.bat 或 uploader.py 开始上传, 成功后即可使用了。

Chrome用户通过[Proxy SwitchySharp](https://chrome.google.com/webstore/detail/proxy-switchysharp/dpplabbmogkhghncfbfdeeokoefdjegm)管理使用Goa能更节省流量。如果你也使用Dropbox的客户端，就在客户端的选项里代理那一栏，选择手动，代理服务器类型为`HTTP`,服务器为：`127.0.0.1:8087`。