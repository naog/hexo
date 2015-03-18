title: 自主控制自启动软件们
date: 2014-11-28
categories: 善用佳软
tags: AHK
permalink: 5
---

经常使用电脑并试用各种软件的我，对自动添加随系统启动的流氓软件深表痛恨，各种流氓软件拍扁了脑袋抢占资源启动自己，开机先卡个两分钟才能使用电脑。但是我只是需要用你们的时候才会打开你们而已，于是乎全部禁用。

AHK全称Autohotkey，是个自动化的好软件，我虽然不是很精通，但是三两句小白代码足以实现自主控制自启动软件的需要。

```
Sleep 3000
	Run D:\ATOM\Listary\Listary.exe
Sleep 5000
	Run D:\INT\ADM\ADM.exe
ExitApp
```

代码说明：等候3000毫秒启动Listary.exe，再等候5000毫秒启动ADM.exe，再等候5000毫秒启动Dropbox.exe，然后退出自己。最后用AHK自带的"ahk2exe"转换成一个exe文件，并加入到开机自启中即可。