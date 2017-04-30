---
title: 百度地图autocomplete导致angular双向绑定失效
---
* 跟autocomplete不兼容。百度地图提供的autocomplete组件用来根据关键词搜索地点，今天遇到一个问题就是发现angular的双向绑定不起作用了。我一开始没有将问题定位到autocomplete这边，一直以为是其他的问题导致双向绑定不起作用了，后来才怀疑到autocomplete这个组件上来(采用代码注释的方式，找到的原因)。原来autocomplete组件会导致输入框的值会被清空，可是照理说清空之后，双向绑定之后模型的数据应该也为空才对呀，可是模型的数据没有清空。然后只能重新设置输入框的值，而且不能马上设置，发现马上设置，值也会被清空，所以要使用angular里面的神器`$timeout`,这个定时器可以帮助我们解决大部分的双向绑定失效的问题。具体用法如下:
```
  var ac = new BMap.Autocomplete({
    "input" : element[0]
  });
  $timeout(() => {
    element.val(scope.address);
    ac.hide();
  });
```
* 百度地图打开出现，图层没有铺满区域的问题。同样使用$timeout将整个调用百度地图的代码放到$timeout里面，然后就能解决问题。
