title: 禁止视频网站使用Flash上传
date: 2015-03-08
categories: 善用佳软
tags: Flash
permalink: 12
---

方法1：控制面板 - Flash Player - 播放 - `阻止所有站点使用对等协助网络`。

方法2： 打开[这个网址](http://www.macromedia.com/support/documentation/cn/flashplayer/help/settings_manager09.html)勾选`对所有用户禁用P2P上行链`。

方法3：在CMD中依次输入以下命令:
```
echo RTMFPP2PDisable=1 >> %windir%\system32\Macromed\Flash\mms.cfg
echo RTMFPP2PDisable=1 >> %windir%\syswow64\Macromed\Flash\mms.cfg
echo RTMFPP2PDisable=1 >> %windir%\system32\mms.cfg
```