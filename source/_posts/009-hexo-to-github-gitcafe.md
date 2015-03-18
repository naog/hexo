title: 把Hexo同时部署到GitHub和GitCafe
date: 2015-01-07
categories: 代码笔记
tags: Hexo
permalink: 9
---

今天又把Hexo折腾了一下，让其可以同时部署到国外的GitHub和国内的Gitcafe，等于是在国内增加了一个镜像，再通过DNSPod智能解析域名，让电信联通教育网的用户访问到托管在GitCafe的Hexo，否则访问到GitHub，一是优化了在国内的速度，二是给数据增加多一个备份。

实现这个功能首先要在GitCafe获得一个帐号（使用的用户名和邮箱最好与GitHub的一致），添加SSH Key，建立与用户名一样的`repo`，可以参见之前的小文：[快速开始Hexo的正确姿势](/7.html)，其次，我们需要修改Hexo仓库根目录下的`_config.yml`文件，打开并拉到最后，修改成这个样子（在GitCafe中，需要注意大小写）:

```
deploy:
  type: git
  repo:
    github: https://github.com/jack/jack.github.io.git,master
    gitcafe: https://gitcafe.com/jack/jack.git,gitcafe-pages
```

随后执行`hexo d -g`生成部署命令的时候，数据就会自动部署到两家平台，这时候，你的GitCafe版的Hexo地址是`jack.gitcafe.io`。尝试这分别`ping`一下两家平台提供的二级域名，会发现GitCafe确实比GitHub快了许多。为了让它自动选择平台，需要在[DNSPod](https://www.dnspod.cn/)相应的域名管理页，分别设置两种八项解析记录，：

<center>[![域名解析设置](http://dn-xair.qbox.me/img/00801.png)](http://dn-xair.qbox.me/img/00801.png)<br/>域名解析设置</center>

其中，GitHub指向的记录值为`nusername.github.io.`，而GitCafe需要在项目设置中添加自定义域名，解析里指向`gitcafe.io.`，这里不推荐直接绑定IP，因为用`CNAME`的方式，两个平台会根据用户位置而自动分配链接到最近的服务器，以保证页面是最快速度呈现，这也算是同时使用了两个平台的CDN吧。

PS.既然已经把Hexo同时部署到了两个Git平台，那么顺便说说如何把Hexo同时备份到两个平台，打开目录文件`.git\config`，添加以下代码：

```
[remote "all"]
	url = https://github.com/jack/jack.git
	url = https://gitcafe.com/jack/jack.git
```

在以后需要`push`备份的时候，只需要执行`push all master`就会同时备份到两家平台，多了一份保障。

如果觉得每次部署的时候都要输入用户名和密码，可以这样解决：在`C:\Users\Administrator`目录下新建一个`_netrc`文件，在里面写上:

```
machine github.com
login user
password userpassword
machine gitcafe.com
login user
password userpassword
```

此后再部署的时候，就不需要再输入两家的用户和密码了。