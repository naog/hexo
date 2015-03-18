title: 自定义Win7&8任务栏图标尺寸 顺带减少窗口边框
date: 2014-11-28
categories: 善用佳软
tags: 注册表
permalink: 4
---

新装好的Windows7或Windows8系统，当设置任务栏按钮为"从不合并"的时候，按钮的宽度是自定义调节的，如果同时打开的任务过多，还会挤的不可开交。窗口的边框的宽度也是离谱。这里需要手动改造一下。

打开注册表，打开到：`HKEY_CURRENT_USER\Control Panel\Desktop\WindowMetrics`分别改动"MinWidth" 任务栏宽度、"PaddedBorderWidth"边框填充宽度、"BorderWidth"边框宽度，这三项为想要的数值。写成一个注册处理语法：

```
Windows Registry Editor Version 5.00
;边框宽度与任务栏图标的宽度
[HKEY_CURRENT_USER\Control Panel\Desktop\WindowMetrics]
"MinWidth"="54"
"PaddedBorderWidth"="0"
"BorderWidth"="0"
```

经测试，"MinWidth"="54"为任务栏图标按钮最佳宽度。