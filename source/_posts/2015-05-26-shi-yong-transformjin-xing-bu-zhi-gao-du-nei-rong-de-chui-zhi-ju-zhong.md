---
title: 使用transform的translate进行居中
---
今天看到一个[网站](http://www.mobilebone.org/)
看到里面的主要内容会根据屏幕高度的变化而自动变化，始终处在垂直居中的位置，然后查看了源码，发现里面有`top: 50%;`
![](/content/images/2015/05/BF379848-9DEE-4737-B94F-988A02A3F8C1.png)
我就奇怪了，为什么使用`top: 50%;`还会居中呢？看里面的写法，应该使用绝对定位，然后left, right, top和bottom为0，设置高度和宽度，然后`margin: auto`,才可以的呀，不过我又注意到下面的transform的写法，发现了`translateY(-50%)`的写法，我才意识到可能是另一种垂直居中方式，果断去google了一下，发现还真有人总结了这样的方法，[点击查看](http://zerosixthree.se/vertical-align-anything-with-just-3-lines-of-css/)
