---
title: javascript事件简介
---
### 概念
事件流描述的是从页面中获取事件的顺序。事件流属于在DOM(文档对象模型)的事件定义中。DOM的定义模型描述(API)经历过好几级变化。从DOM0级到DOM3级[历史](http://segmentfault.com/a/1190000000366311)。关于时间的定义主要在DOM0级和DOM2级里面有定义。*现在支持DOM0级的浏览器主要是IE8，像IE9, Firefox, Opera, Safari和Chrome都全部已经实现了"DOM2级事件"模块的核心部分。IE8是最后一个仍然使用其专有事件系统的主要浏览器。*(来自Javascript高级程序设计)

### 描述
DOM0级的核心设置事件处理程序的方法:
```
var btn = document.getElementById('myBtn');
btn.onclick = function() {
  alert(this.id);
}
```
DOM2级描述的核心设置事件处理程序的方法:(可以传入第三个参数，表示事件捕捉时在捕获阶段还是在冒泡阶段进行，true表示是捕获阶段，false或者不传表示是冒泡阶段进行捕获)
```
var btn = document.getElementById('myBtn');
btn.addEventListener('click', function() {
  alert(this.id);
});
```

这边也给出IE8实现的独特的添加事件处理程序的方法:
```
var btn = document.getElementById('myBtn');
btn.attachEvent('click', function() {
  alert(this.id);
});
```
区别就是将`addEventListener`改为`attachEvent`方法。

### 注意
1、DOM0级设置的方式触发的事件处理程序只会执行一遍，但是通过addEventListener可以添加多个事件处理程序，也就是说使用addEventListener添加了多个点击事件的触发程序，那么这个元素被点击的时候就会按照当时定义的顺序触发这些触发程序，但是DOM0的方法不会，所以DOM0级要取消触发程序只需要`btn.onclick = null`就好了。
2、假如同时给一个元素使用DOM0级和DOM2级定义的方法进行设置事件处理函数的时候，DOM2级的设置会失效，只会生效DOM0级的设置事件。

### 参考 《Javascript高级程序设计》
