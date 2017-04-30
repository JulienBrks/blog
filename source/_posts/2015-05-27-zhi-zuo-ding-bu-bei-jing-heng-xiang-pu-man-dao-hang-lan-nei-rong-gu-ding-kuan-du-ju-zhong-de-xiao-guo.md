---
title: 导航栏背景铺满，内容居中的方案
直接上结构

```
   <header>
      <div id="header-content"></div>
   </header>
```

样式

```
    header {
         background-color: #fff;
         min-width: 990px; // 里面内容的固定宽度, 假如不设置最小宽度的话，假如浏览器的屏幕宽度小于990px时会发生滚动条向右滚动的时候出现白色的区域，也就是说其实header的宽度没有达到990px，所以需要设置最小宽度为990px。
    }
    header #header-content{
        width: 990px;
        margin: 0 auto;
    }
```
上自家公司的导航栏:)![自家公司的导航栏](/content/images/2015/05/7A07E1F8-8B6F-4949-8888-941D00BA998E.png)

向右边滚动的效果哦
![](/content/images/2015/05/43B278CF-3E92-420E-A7D9-96D6970D1B1A.png)
