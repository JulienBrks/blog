本文为这一篇[文章](http://www.cnblogs.com/2050/p/3877280.html)的总结。

感谢这一篇[文章](http://tgideas.qq.com/webplat/info/news_version3/804/7104/7106/m5723/201509/376281.shtml)提供了关于iphone的dpi的数据和google定义的dpi的说明数据。

#### viewport是什么?
设置的区域它包括我们在手机屏幕可视的区域加上假如有滚动条的情况下，隐藏的区域。

#### 怎么使用兼容性更好?
为了能够让各个平台的手机浏览器支持viewport的设置，使用`<meta name="viewport" content="width=device-width, initial-scale=1">`，这样能够保证各个平台的浏览器在竖屏和横屏的情况下都能够保持viewport的跨度为整个手机屏幕的宽度（一般高度我们不会做设置）。

##### 使用`<meta name="viewport" content="width=device-width, initial-scale=1">`的一个显而易见好处？
目的是为了保持页面在各个分辨率的手机浏览器上面显示效果保持一致。通过计算发现iphone4，iphone5, iphone6和使用上面的设置，也就是说100px宽的盒子显示在上面三个手机上的宽度是几乎一样的（iphone6 plus不太一样，不过也相差不大），假如我们设置width=自己设置的一个值，那么就会发现一样的页面在不同的手机分辨率下面呈现的大小不一样，而这不是我们想要看到的。


Ps: 每一英寸呈现的css像素值的计算方式是 `dpi / (widthPixel / device-width)`。 这里的widthPixel表示该机型的在宽度上的物理像素值，device-width表示这个机型应用`<meta name="viewport" content="width=device-width, initial-scale=1">`这句话之后屏幕视窗在宽度上呈现的css像素值。
