title: 让Mactype在×64的Chrome下正常渲染
date: 2014-11-17
categories: 善用佳软
tags: Mactype
permalink: 2
---

`Update:2014.11.28` 在<chrome://flags/>中启用`停用DirectWrite`，即可渲染。

自从用了Mactype这个媲美Mac OS渲染神器，从Win XP到Win8.1，每次装好系统第一件事就是安装调试Mactype，没有这货，Win平台的字体兼职刺瞎狗眼。但是升级到64位Win8.1后，问题就出现了。不能渲染IE这就不说了，但是我作为一个重度Chrome用户，除了Chrome不会用其他的浏览器，Mactype在64位Win8.1下，居然把网页渲染成了这个狗样子！

<center>[![使用前](http://dn-xair.qbox.me/img/00201.png)](http://dn-xair.qbox.me/img/00201.png)<br/>使用前</center>

岂能让这等惨不忍睹的页面出现在我的屏幕，无渲染的页面也是入不了眼的，于是开始曲线救国，让精美的渲染字体重回眼底。

Mactype的配置文件中，有一项`[ExcludeSub]`解释为不进行热替换字体的程序，但会渲染字体。先把`Chrome.exe`添加到该项的下一行。然后在浏览器的设置中进行替换字体就可以了。

Chrome的应用商店有很多可以设置页面字体的扩展，我首先用了强大的Stylish，固然强大，但是加载页面的时候会有一秒的延迟，弃之，经过再三比较，选用了一款叫做<a href="https://chrome.google.com/webstore/detail/%E5%BC%BA%E5%88%B6%E4%BD%BF%E7%94%A8%E5%BE%AE%E8%BD%AF%E9%9B%85%E9%BB%91%E5%AD%97%E4%BD%93%C2%B7%E5%AE%8C%E7%BE%8E%E7%89%88/jjeknnigbkhhilfjhoijbddeaihdpmdi" target="_blank">强制使用微软雅黑字体</a>的扩展。

默认会把网页中所有字体替换成雅黑字体，Mactype会渲染它。如果你喜欢其他字体，就要进一步修改了。

安装后，在<chrome://extensions/>中会显示这个扩展的ID： jjeknnigbkhhilfjhoijbddeaihdpmdi，记录下来。打开扩展所在的文件夹，`C:\Users\***\AppData\Local\Google\Chrome\User Data\Default\Extensions\jjeknnigbkhhilfjhoijbddeaihdpmdi\`，在里面找到`custom.css`，这就是控制字体的样式表了。在里面写入：

```css
* {font-family: "XHei OSX" !important;}
```

XHei OSX 是我替换的字体，你可以替换任意字体。这时，再打开网页，字体就会变成了这样。

<center>[![使用后](http://dn-xair.qbox.me/img/00202.png)](http://dn-xair.qbox.me/img/00202.png)<br/>使用后</center>

但是有些网页使用了webfont，即图标文字，如淘宝、支付宝、天猫等，或代码块区域，这时候我们要在全局字体的下面加入一些例外。

```css
/* for taobao.com, alipay.com, tmail.com */
.iconfont {font-family: "iconfont", "shop-iconfont", "global-iconfont", "global", "uxiconfont", "rei" !important;}
.mui-iconfont {font-family: "mui-iconfont", "iconfont", "shop-iconfont", "global-iconfont", "uxiconfont", "rei" !important;}
a .icon {font-family: "vip-font", "iconfont", "shop-iconfont", "global-iconfont", "uxiconfont", "rei" !important;}
/* for github.com */
span .octicon {font-family: octicons !important;}
/* for Code */
pre, code, textarea, tt, kbd, samp,pre *, code *, textarea *, tt *, kbd *, samp * {font-family: Consolas,Stxihei !important;}
```

.iconfont之类是使用webfont元素的class，如果你不习惯这样太过于强制的方式，可以尝试用下面的方法单独替换字体。

```css
@font-face {font-family: '宋体'; src: local('XHei OSX');}
@font-face {font-family: '宋体'; src: local('XHei OSX');}
@font-face {font-family: 'SimSun'; src: local('XHei OSX');}
@font-face {font-family: 'SimSun'; src: local('XHei OSX');}
```

以上语句只会单独替换宋体，但是写法要注意，中西文的字体名字都要写上，不需要特别声明粗体，举一反三写之。