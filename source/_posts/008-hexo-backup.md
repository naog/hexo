title: Hexo的备份和恢复
date: 2015-01-03
categories: 代码笔记
tags: Hexo
permalink: 8
---

在2015年的第一天，我寻思给电脑也清理一下过个元旦吧，然后就手欠把主板CPU针脚干断两根，推到一片，主板送修后把硬盘接到了家用的另外一台电脑，恰遇如何备份和恢复Hexo的问题，这里便记录一下这个情况，高手可以直接无视。

###备份Hexo的两种方式
第一种方式比较简单，直接把Hexo的文件夹放进Dropbox或其他同步盘里，在重装系统或另外一台电脑同步下来就行了。

第二种方式是备份到Github，这就需要费点周折了，不过这也是学习Git命令的好机会。首先需要在GitHub建立一个新的仓库，如Hexo。在本地的Hexo文件夹里执行Git命令：
```
$ git init  //初始化仓库
$ git remote add origin https://github.com/jack/hexo.git  //关联远程仓库
$ git add .  //添加所有文件到缓存
$ git commit -m "add all file" //提交"说明"
$ git push -u origin master  //第一次推送到远端仓库
```
这是第一次备份整个Hexo文件夹到GitHub的命令集合（根目录下有个.gitignore文件，里面每行的文件或文件夹都是不会提交到Git的，这里推荐把node_modules文件夹去掉，这里是Hexo的依赖库），由于我们经常写文章，同样需要把新写的文章备份进去，当然，还有Hexo的主题改动。以后有改动或更新再次备份的时候，就会简单一些:
```
$ git add .
$ git commit -m "add new post"
$ git push origin master	//第一次后每次推送修改到远端仓库master分支
```
到这里，整个Hexo算是备份到GitHub了，一般只是用来添加新文章和文章改动，如果需要更多的功能，建议查阅一下这两个Git文档:[Git 参考手册](http://gitref.org/zh/index.html)和[廖雪峰的Git教程](http://www.liaoxuefeng.com/wiki/0013739516305929606dd18361248578c67b8067c8c017b000)。

###恢复Hexo
第一种备份方式直接同步下来就可以了，而第二种则需要先安装必要的环境[Git](http://msysgit.github.io/)和[Node.js](http://nodejs.org/)和SSH Key，参见前一篇小文[快速开始Hexo的正确姿势](/7.html)，顺便先设置用户信息、安装Hexo：
```
$ git config --global user.name "jack"//用户名
$ git config --global user.email  "jack@gmail.com"//你的邮箱
$ npm install -g hexo
```

然后只需一条命令即可从GitHub克隆回来：

```
$ git clone https://github.com/jack/hexo.git
```
这时候你的Hexo已经满血复活了，又可以快乐的Hexo了。
