title: 我的Chrome浏览器相关配置
date: 2015-01-30
categories: 善用佳软
tags: Chrome
permalink: 11
---
本人是Chrome重度用户，这里贴一下Chrome的相关配置，以防日后丢失数据后可方便找回。

### chrome://flags/
- 启用 停用DirectWrite Windows (mactype渲染)
- 启用 实验性 QUIC 协议
- 启用 启用SPDY/4

### Chrome强制http定向到https
打开到`chrome://net-internals/#hsts` 在Add Domain 项的Domain中写入域名，同时勾选`Include subdomains for STS/KPK` 然后Add即可，删除域名就在下面的Delete Domain中写入并Delete

### Tampermonkey脚本
- [BaiduSearchNoJump modify](https://greasyfork.org/zh-CN/scripts/7152-baidusearchnojump-modify-by-ted423)
- [知乎免登录](http://tiansh.github.io/us-else/zhihu_visitor/)
- [数据银行下载助手](https://greasyfork.org/zh-CN/scripts/3193-%E6%95%B0%E6%8D%AE%E9%93%B6%E8%A1%8C%E4%B8%8B%E8%BD%BD%E5%8A%A9%E6%89%8B)
- [百度网盘助手](https://greasyfork.org/zh-CN/scripts/986-%E7%99%BE%E5%BA%A6%E7%BD%91%E7%9B%98%E5%8A%A9%E6%89%8B)
- [百度音乐助手](https://greasyfork.org/zh-CN/scripts/483-%E7%99%BE%E5%BA%A6%E9%9F%B3%E4%B9%90%E5%8A%A9%E6%89%8B)
- [百度音乐盒去广告](https://greasyfork.org/zh-CN/scripts/2248-%E7%99%BE%E5%BA%A6%E9%9F%B3%E4%B9%90%E7%9B%92%E5%8E%BB%E5%B9%BF%E5%91%8A)
- [解除贴吧必需登录才能浏览的限制](https://greasyfork.org/zh-CN/scripts/5999-%E8%A7%A3%E9%99%A4%E8%B4%B4%E5%90%A7%E5%BF%85%E9%9C%80%E7%99%BB%E5%BD%95%E6%89%8D%E8%83%BD%E6%B5%8F%E8%A7%88%E7%9A%84%E9%99%90%E5%88%B6)
- [虾米音乐助手](https://greasyfork.org/zh-CN/scripts/987-%E8%99%BE%E7%B1%B3%E9%9F%B3%E4%B9%90%E5%8A%A9%E6%89%8B)

### Chrome扩展
- [Enable Copy](https://chrome.google.com/webstore/detail/enable-copy/lmnganadkecefnhncokdlaohlkneihio?utm_source=chrome-app-launcher-info-dialog) 解除右键限制
- [Google Keep](https://chrome.google.com/webstore/detail/google-keep-notes-and-lis/hmjkmjkepdijhoojdojkdfohbdgmmhki?utm_source=chrome-app-launcher-info-dialog) 记事和清单
- [IE Tab](https://chrome.google.com/webstore/detail/hehijbfgiekmjfkfjpbkbammjbdenadd?utm_source=chrome-app-launcher-info-dialog) IE内核模式
- [LastPass](https://chrome.google.com/webstore/detail/lastpass-free-password-ma/hdokiejnpimakedhajhdlcegeplioahd?utm_source=chrome-app-launcher-info-dialog) 密码管理
- [Proxy SwitchyOmega](https://chrome.google.com/webstore/detail/padekgcemlokbadohgkifijomclgjgif?utm_source=chrome-app-launcher-info-dialog) 代理切换
- [QQ收藏](https://chrome.google.com/webstore/detail/ggllcioagamdajojjpjanhhbdknngbdh?utm_source=chrome-app-launcher-info-dialog)
- [Replace Google CDN](https://chrome.google.com/webstore/detail/kpampjmfiopfpkkepbllemkibefkiice?utm_source=chrome-app-launcher-info-dialog) Google CDN转向
- [scroll style](https://chrome.google.com/webstore/detail/lcfiapjcgfnalnpmgfoebehefdeekado?utm_source=chrome-app-launcher-info-dialog) 顺滑滚动蓝
- [Stash](https://chrome.google.com/webstore/detail/stash/bnhjedgfogckebfhnlicnkbdjlmpibck?utm_source=chrome-app-launcher-info-dialog) 暂存标签页
- [Tampermonkey](https://chrome.google.com/webstore/detail/dhdgffkkebhmkfjojejmpbldmpobfkfo?utm_source=chrome-app-launcher-info-dialog) 油猴脚本
- [Text URL Linker](https://chrome.google.com/webstore/detail/text-url-linker/aegfbpchoheaflicfmggkmlmcccpjpgd?utm_source=chrome-app-launcher-info-dialog) 转换网址成超链接
- [v2ex.ext](https://chrome.google.com/webstore/detail/cibnlngbgpkcmbiilfdeekaojmfhimag?utm_source=chrome-app-launcher-info-dialog) V2EX专享
- [Happy YaHei](https://chrome.google.com/webstore/detail/jjeknnigbkhhilfjhoijbddeaihdpmdi?utm_source=chrome-app-launcher-info-dialog) 强制雅黑
- [划词翻译](https://chrome.google.com/webstore/detail/%E5%88%92%E8%AF%8D%E7%BF%BB%E8%AF%91/ikhdkkncnoglghljlkmcimlnlhkeamad/support)
- [支付宝安全插件](https://chrome.google.com/webstore/detail/lapoiohkeidniicbalnfmakkbnpejgbi?utm_source=chrome-app-launcher-info-dialog)
- [百度识图](https://chrome.google.com/webstore/detail/%E7%99%BE%E5%BA%A6%E8%AF%86%E5%9B%BE/ckphchjljlekndhjifdfpmmnlaijimcd?utm_source=chrome-app-launcher-info-dialog)
- [网页截图:注释&批注](https://chrome.google.com/webstore/detail/alelhddbbhepgpmgidjdcjakblofbmce?utm_source=chrome-app-launcher-info-dialog)
- [迅雷、快车、旋风专用链自动转换绿色版](https://chrome.google.com/webstore/detail/%E8%BF%85%E9%9B%B7%E3%80%81%E5%BF%AB%E8%BD%A6%E3%80%81%E6%97%8B%E9%A3%8E%E4%B8%93%E7%94%A8%E9%93%BE%E8%87%AA%E5%8A%A8%E8%BD%AC%E6%8D%A2%E7%BB%BF%E8%89%B2%E7%89%88/keoppklbljbnecjcpehjlmdcdibpdclf?utm_source=chrome-app-launcher-info-dialog)