title: Markdown语法备忘录
date: 2014-11-16
categories: 代码笔记
tags: Markdown
permalink: 1
---

常用的写作标记：

```
<h1>ex</h1> | #ex  （1~6个#对应H1~H6）
<em>ex</em> | *ex* | _ex_
<strong>ex</strong> | **ex** | __ex__
```

如果 * 和 _ 两边都有空白则作普通符号，如果要在文字前后直接插入普通的星号或底线，你可以用反斜线：

```
<p>*Someone* like you.</p>
	>code:  \*Someone\* like you.
```

各种链接的转换,省略了url中的`http://`。

```
<a href="ex.com">EX</a>
	>code:  [ex](ex.com)
    	<a href="ex.com">ex.com</a>
        	>code:  <ex.com>
<img src="http://www.ex.com/img.jpg" alt="LOGO">
	>code: ![LOGO](http://www.ex.com/img.jpg)
        <img src="http://www.ex.com/img.jpg" alt="LOGO" title="LOGO">
            >code:  ![LOGO](http://www.ex.com/img.jpg "LOGO")
<a href="http://ex.com"><img src="http://www.ex.com/img.jpg" alt="LOGO"></a>
	>code:  [![LOGO](http://www.ex.com/img.jpg)](http://ex.com)
```

Markdown语法无法定义图片尺寸，但是可以直接写入HTML语言，以此来定义图片尺寸、链接中的target属性、视频（优酷的一个例子）等：

```
<a href="ex.com" target="_blank">EX</a>
	<a href="ex.com" target="_blank" class="style">EX</a>
<img src="http://www.ex.com/img.jpg" alt="LOGO" width="270" height="129">
<embed src="http://player.youku.com/player.php/sid/XNDgzMTI4MjQ0/v.swf" allowFullScreen="true" quality="high" width="632" height="527" align="middle" allowScriptAccess="always" type="application/x-shockwave-flash"></embed>
```

在代码片段中， `′′′`内的语句只用来展示，不会执行。language是声明语言的标记，可以使`′′′`、CSS、MARKDOWN任意语言。也可以用4个空格或1个Tab代替：

```
<pre>
 <code>
  <div class="exclass">This is code</div>
 </code>
</pre>
------------------------------------------------
′′′language
 <div class="exclass">This is code</div>
′′′
```

当需要在文章中使用一句短代码的时候。使用 `′` 或 `′′` ,或者直接用 `<code>` ：

```
<p>Just blockqute a <code>Short code</code> example</p>
--------------------------------------------------------
    Just blockqute a `Short code` example
	or
    Just blockqute a ``Short code`` example
	or
    Just blockqute a <code>Short code</code> example
```


引用 Blockquotes  段首加 `>`，引用内可用其他的markdown语法：

```
<blockquote>
	<p>Blockquotes something</p>
</blockquote>
---------------------------------
>Blockquotes something
```

无序的 `ul`、`li` 列表，段首用 `*`、`+`、`-`，后跟一个 `空格`:

```
<ul>
 <li>List 1</li>
 <li>List 2</li>
 <li>List</li>
</ul>
--------------------
* List 1
+ List 2
- List 3
```

带上1.2.3.的有序的 `<ol>`、`<li>` 列表，则在开头使用 `数字`+ 句点`.` + `空格`：

```
<ol>
 <li>List 1</li>
 <li>List 2</li>
 <li>List</li>
</ol>
--------------------
1. List 1
2. List 2
3. List 3
```

如果列表项目间用空行，在输出`′′′`时Markdown就会将项目内容用 `<p>` 标签包起来，举例来说：

```
<ul>
    <li><p>Bird</p></li>
    <li><p>Magic</p></li>
</ul>
-------------------------
* list 1
　
* list 2
```