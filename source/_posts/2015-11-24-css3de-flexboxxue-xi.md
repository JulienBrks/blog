---
title: flexbox介绍
---
### 介绍
摘自w3cschool的关于flexbox的介绍
```
Use of flexbox ensures that elements behave predictably when the page layout must accommodate different screen sizes and different display devices.
```
它主要确在不同的宽度和显示设备情况下元素能够符合预期地进行调整。  
它主要用来完成分栏布局，相当于css2使用block+float完成的分栏布局。
### 相比CSS2使用block+float的优点

* 跟一个元素定义为`display: flex;`假如没有定义`flex-direction`或者`flex-direction`定义为`row`，那么它的直接儿子可以在高度上自动铺满它高度。否则它的直接儿子可以在宽度上面自动铺满。

* 它不会存在margin塌陷的问题, 怎么会出现这个问题以及解决办法请查看[这篇文章](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Box_Model/Mastering_margin_collapsing)

### 参考
[w3c关于flexbox的介绍](http://www.w3schools.com/css/css3_flexbox.asp)
