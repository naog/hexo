title: 提高Listary启动程序的命中率
date: 2014-11-18
categories: 善用佳软
tags: Listary
permalink: 3
---

作为一个桌面图标多了会死星人，我习惯用热键呼出Listary框打开需要的软件，但Listary默认的搜索结果有点不尽人意，原因有3：

- 很多软件的安装目录含有多个相似名称的文件
- Listary可以智能匹配字母对应拼音，且匹配任意位置
- Listary会把所有匹配的文件、文件夹一同展示

以上三个原因，造成通过Listary启动应用程序的命中率不足，或需要更多的按键动作（上下选取）才能打开所需软件，岂不是还不如直接桌面戳图标来的更有效率？是不是要换成其他的快速启动软件，可其他的快速启动软件又不能快速搜索全磁盘文件……

换一个已经上手的高频率使用的软件是个更纠结的问题，只需两步手动设置，就可以使Listary启动程序的命中率提高到99%~100%，且按键更少。

第一步：把电脑上装的所有软件的快捷方式（常用文件夹也可以）放到同一个文件夹，如`D:\run\`，并把快捷方式的名字改成2-3个字母，如我把Dropbox改成DB，把Photoshop改成PS，中文也可以，因为Listary能匹配拼音。

<center>[![建立快捷方式库](http://dn-xair.qbox.me/img/00301.png)](http://dn-xair.qbox.me/img/00301.png)<br/>建立快捷方式库</center>

第二步：打开Listary选项菜单，切换到`启动程序`项，把默认自带的`%star_menu%`到`%default_launch%`前面的`√`去掉，再把`D:\run\`加进去。

大功告成，之后启动Photoshop只需在呼出Listary后按PS就可以回车键打开了，命中率几乎100%，如果安装的软件实在太多，建议把快捷方式的名字改成3~5个字母。

<center>[![输入简单的字母](http://dn-xair.qbox.me/img/00302.png)](http://dn-xair.qbox.me/img/00302.png)<br/>输入简单的字母</center>