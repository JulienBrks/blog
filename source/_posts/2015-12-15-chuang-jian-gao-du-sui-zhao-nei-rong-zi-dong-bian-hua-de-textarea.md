昨天有一个同事遇到一个问题，那就是设计师要求输入框(也就是textarea)的高度能够随着内容高度的变化而变化，也就是不出现垂直方向上的滚动条。

然后他尝试通过设置定时器让textarea的高度始终等于scrollHeight解决这个问题:

```
setInterval(function() {
	document.getElementById('textarea').style.height = document.getElementById('textarea').scrollHeight;
});
```

不断输入内容，高度增加的时候，确实textarea的高度也增加了。但是内容减少的时候，发现textarea的高度却不会减少。这是由于scrollHeight的高度其实反应着height的高度，textarea内容的高度减少，不能减少scrollHeight的值。
例子如下:
<iframe width="100%" height="300" src="//jsfiddle.net/JulienBrks/d9yna9fa/5/embedded/" allowfullscreen="allowfullscreen" frameborder="0"></iframe>

#### 我的解决方式:

由于不能获取textarea的内容高度，所以我想到使用一个p标签模拟textarea，始终保持p标签的内容跟textarea的内容一样，然后获取p标签的高度设置textarea的高度，就能够让textarea的高度随着内容高度变化二自动变化了。 
例子如下:
<iframe width="100%" height="300" src="//jsfiddle.net/JulienBrks/nc2gcemv/6/embedded/" allowfullscreen="allowfullscreen" frameborder="0"></iframe>


#### 注意:

1、p标签和textarea的字体，字号，宽度，行高，word-break样式保持一致
2、p标签要保证`white-space: pre-wrap`，这样回车的时候也能够让p标签的高度增加

#### 存在的问题:

1、p标签存在连续多个回车的时候，textarea会出现滚动条，由于textarea最后一个回车会占一行，但是p标签不会。