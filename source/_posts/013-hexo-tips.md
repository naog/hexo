title: Hexo Tips 持续贴
date: 2015-03-13
categories: 代码笔记
tags: Hexo
permalink: 13
---

Hexo 3.0 Bug 略多，降级到2.8：
```
npm uninstall hexo hexo-cli hexo-server hexo-generator-index hexo-generator-archive hexo-generator-category hexo-generator-tag hexo-deployer-git hexo-generator-feed hexo-generator-sitemap hexo-renderer-marked hexo-renderer-stylus
*****
npm install -g hexo@2.8.3
hexo init
npm install
*****
卸载高版本插件&安装指定版本插件
npm uninstall hexo-renderer-ejs hexo-renderer-marked hexo-renderer-stylus
npm install hexo-renderer-ejs@0.1.0 hexo-renderer-marked@0.1.0 hexo-renderer-stylus@0.1.0 hexo-generator-feed@0.2.1 hexo-generator-sitemap@0.2.0
*****
npm install hexo-gzip
``` 

Hexo更新到了3.0版本，较以往的使用上出现了个别问题，在[快速开始Hexo的正确姿势](/hexo-start.html#安装Hexo)中的三依次命令，改为:
```
npm install hexo-cli -g
npm install hexo --save
hexo init
npm install
```
然后安装常用插件与配置:
```
npm install hexo-server --save
npm install hexo-generator-index --save
npm install hexo-generator-archive --save
npm install hexo-generator-category --save
npm install hexo-generator-tag --save
npm install hexo-deployer-git --save
******************************************
npm install hexo-deployer-heroku --save
npm install hexo-deployer-rsync --save
npm install hexo-deployer-openshift --save
```

换行符的问题:
```
hexo warning: LF will be replaced by CRLF in XXX.
解决方法：
git config --global core.autocrlf false
```

index.lock问题:
```
fatal: Unable to create ‘/.git/index.lock’: File exists.
解决方法：
rm -f index.lock
```