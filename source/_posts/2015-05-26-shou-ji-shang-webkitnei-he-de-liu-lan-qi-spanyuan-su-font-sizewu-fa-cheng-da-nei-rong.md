---
title: 手机上行内元素无法设置font-size的问题
---
今天在safari浏览器上开发官网发现有一个span元素始终无法设置font-size。在网上搜索后发现webkit浏览器会有私有的-webkit-text-size-adjust属性，用于自动调整字体，方便阅读。

解决方式:

* 可以使用`-webkit-text-size-adjust: none`则可以禁用浏览器的字体自动调整。
* 可以将span元素的css属性display-block, 浏览器不会对对内表现为block的元素的字体进行自动调整。
