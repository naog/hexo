title: 快速开始Hexo的正确姿势
date: 2014-12-24
categories: 代码笔记
tags: Hexo
permalink: 7
---

Hexo是很好的文章管理工具，一经使用我已经爱不释手。看过各种Hexo的安装教程之后，本码盲也成功召唤了一头Hexo坐骑，但是回头想想有些教程的内容过分详细、条例不清晰的原因往往也会给新手（包括我）造成出错的麻烦，于是在此梳理一番（本姿势仅适用于Win平台）。

###开始Hexo前的准备工作
1. 本地必备的环境安装：[Git](http://msysgit.github.io/)和[Node.js](http://nodejs.org/)。
2. 托管Hexo的[GitHub](https://github.com/)账号一枚，并建立一个跟用户名一样的repositories，如用户名为jack则为:jack.github.io
3. 创建连接本地与Github的SSH Key。

依次安装Git和Node.js后，在任意位置右键选择` Git Bash Here `，在命令窗口内以下命令来创建SSH Key:
```
$ ssh-keygen -t rsa -C "jack@gmail.com"	//你的邮箱
```
输入这个命令后，凭着小学本科的英语水平你会看出Git系统要求你输入name啊password啊什么的，这时请啪啪啪一路回车，直到你看见由` + + o O *  = S ` 组成的个图案，说明你创建SSH Key成功了! 打开` C:\Users\Administrator\.ssh ` 发现`id_rsa`和`id_rsa.pub`两个文件，前者是私钥，不能泄露给别人，后者是公钥，也是连接GitHub需要的，把`id_rsa.pub` 内的一堆字母复制到到[Github SSH keys](https://github.com/settings/ssh)设置页面。完事儿以后先测试一下SSH Key是否能连接到GitHub：
```
$ ssh -T git@github.com [yes]
```
当返回一句Hi balabala的之后，说明你已经顺利勾搭上GitHub了，然后还需要设置一下用户信息，就可以安装Hexo了。
```
$ git config --global user.name "jack"//用户名
$ git config --global user.email  "jack@gmail.com"//你的邮箱
```

###安装Hexo
在你需要存放Hexo的文件夹内依次输入以下三个命令，进行`安装hexo`、`初始化Hexo`和`安装Hexo依赖包`。
```
$ npm install -g hexo
$ hexo init
$ npm install
```
然后打开根目录下的_config.yml文件，找到`deploy:`项来配置Hexo。
```
deploy:
  type: github
  repository: https://github.com/jack/jack.github.io.git
  branch: master
```
现在你的Hexo坐骑已经召唤成功了，呼一口气先，马上就可以坏快的开始Hexo了！

###使用Hexo
如果你也同样不熟悉Git命令，那么就直接把写好的`.md`格式的文章丢到`\source\_posts`文件夹吧，当然你需要在这些文章的页头加上Hexo认识的标记，如本文为例，页头标记是这样的:
```
---
title: 快速开始Hexo的正确姿势	//标题
date: 2014-12-24		// 日期
categories: 代码笔记		//文章分类
tags: Hexo			//文章tags
permalink: 7			//文章的url别名
---
```
写好文章以后，还要通过命令使Hexo来生成文章、部署到GitHub，不过这些命令是在是太简单了:
```
$ hexo g == hexo generate	//生成
$ hexo d == hexo deploy		//部署
$ hexo s == hexo server		//本地预览
```
在以上命令中`==`符号前面是简写命令，后面是完整命令，一般只需要记住`g 、d 、s`三个就OK了，如果你想本地预览，在输入命令后，打开网址`http://localhost:4000/` 就可以过过眼瘾先了。一般的Hexo步骤是：写文章 → 生成 → 部署/预览。如果你不用预览，可以输入`hexo d -g`直接进行生成部署。

###给Hexo绑定一个域名
绑定域名更是简单，只需在`source`文件夹添加一个`CNAME`文件，里面写上你的域名，然后在域名解析那里建立`CNAME`类型解析到`jack.github.io.`，稍等片刻，即可通过自己的域名访问。

本文介绍了如何快速开始使用Hexo的过程，到此，想必在看本文的你已经成功拥有一个Hexo博客了。本文只是基本的Hexo搭建和使用说明，同是新手的我，在以后也会作文分享在Hexo的使用中遇到的各种问题，例如自定义主题、备份文章等知识，希望我们都能快乐的使用Hexo。

评论模块：
```
THEMES:\_config.yml fix duoshuo_short_name: duoshuoname
THEMES:\layout\_partia\article.ejs #25 
 add <%- partial('comment') %>
```