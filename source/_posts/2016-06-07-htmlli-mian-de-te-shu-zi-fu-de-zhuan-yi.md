---
title: 浏览器转义
---
#### 写这个的背景: 

最近做项目过程中发现有时候后端返回的字符串会是`&lt;script&gt;console.log(&quot;asdf&quot;)&lt;/script&gt;`这样的字符串。然后浏览器会呈现出`<script>console.log("asdf")</script>`。像`&lt;`转化为了`<`，就是浏览器会自动进行转义。

#### 概念

<table>
<thead>
<td>例子</td>
<td>说明</td>
</thead>
<tr>
<td>lt</td>
<td>字符实体</td>
</tr>
<tr>
<td>&amp;lt;</td>
<td>字符实体引用</td>
</tr>
<tr>
<td>#60</td>
<td>数字实体(字符的unicode编码)</td>
</tr>
<tr>
<td>&amp;#60;</td>
<td>数字实体引用</td>
</tr>
<tr>
<td><</td>
<td>浏览器渲染之后的呈现</td>
</tr>
</table>

#### 使用场景

* 由于一些设备无法输入某一些特殊字符，可以使用这种方式在浏览器呈现这样的字符，比如♠字符。
* 会被解释为标记，字符无法直接输入文档，比如回车键。
* 防止xss，具体可以看参考资料的第四篇。

#### 参考资料和工具:

1. [stackoverflow我真的需要转义&为&amp;amp;?](http://stackoverflow.com/questions/3493405/do-i-really-need-to-encode-as-amp)
2. [html转义表](http://www.jb51.net/onlineread/htmlchar.htm)
3. [html在线转义工具](http://www.css88.com/tool/html-escape/)
4. [html转义防止js注入的文章](http://wonko.com/post/html-escaping)
5. [编码转换工具](http://tool.chinaz.com/tools/unicode.aspx)
6. [编码解码工具](http://www.cnblogs.com/txw1958/archive/2013/04/20/unicode-encode-decode.html)
7. [转义的概念详细解释](http://xuqin.blog.51cto.com/5183168/887799)
