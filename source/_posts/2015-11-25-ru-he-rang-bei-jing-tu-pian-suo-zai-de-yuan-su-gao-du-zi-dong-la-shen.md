---
title: 背景图片随图片自动铺满
---
我们知道背景图片的`background-size: cover`可以让元素自动铺满整个元素。但在手机web上面我们经常会遇到这样的问题，那就是手机web的屏幕分辨率五花八门，所以要保证有一些背景元素也能够自适应的进行变化。但是背景图片不是img标签，不会随着元素宽度的变化而可以改变高度(img标签可以通过设置(`width: 一个百分值;height: auto;`来做到。)。为了能够让背景元素也能够进行自动拉伸，保证图片能够按照原来的长宽比例铺满元素，我们需要自动拉伸元素的高度。

今天从stackoverflow发现有一个人是这么解决这个问题的,[链接](http://stackoverflow.com/questions/600743/how-to-get-div-height-to-auto-adjust-to-background-size)。
```
这是该背景元素为如下样式就好了:
div{
    background-image: url('http://www.pets4homes.co.uk/images/articles/1111/large/feline-influenza-all-about-cat-flu-5239fffd61ddf.jpg');
    background-size: contain; /* 这里cover一样，因为元素的长宽比例一样不会出现拉伸比例不一样的情况 */
    background-repeat: no-repeat;
    width: 100%;
    height: 0;
    padding-top: 66.64%; /* (img-height / img-width * container-width) */
                /* (853 / 1280 * 100) */
}
```

这段代码的核心是padding-top, 通过设置一个百分值比的值，让它的高度做到跟宽度一起变化。

下面我们看一下padding-top是百分值在[w3c](http://www.w3school.com.cn/cssref/pr_padding-top.asp)上面的解释:
%:	定义基于父元素宽度的百分比上内边距。
那么只要父元素定义一个宽度，这个背景元素的高度就是父元素宽度* 66.64%, 而这个值就是 X = 父元素宽度 * img-height / img-width。 我们换一下结构， 那么X / 父元素宽度 = img-height /img-width. 所以X的值跟父元素的比例就是图片的长宽比，由于子元素(也就是这边的背景元素)设置了`width: 100%`,所以子元素的宽度就为父元素的宽度，所以我们知道X / 子元素宽度的比例也是图片的长宽比。那么就实现了子元素的高度自动拉伸满足正好图片放大(或者缩小)铺满整个背景元素了。

终于讲完了，假如有什么不明白的可以手机访问123feng.com里面的三个按钮查看元素看一下实现。提醒一下，请使用高版本的手机浏览器，由于使用了一些css3的特性。



