* 模式概要: 模式是用来解决一类普遍问题的解决方案
* Module模式概要: Module模式就是能够产生一种包含私有方法，私有属性，公用方法，公用属性对象的一种解决方案。
javascript钟
* 实现方式如下:
```
var module = (function(){
  var privateProp = 'pp1';
  var privateFunc = function() {
    console.log(privateProp);
  };
  return {
    publicProp: 'pp2',
    publicFunc: function() {
      console.log(this.publicProp);
      console.log(privateProp);
      privateFunc();
    }
  }
})();

module.publicFunc();
module.publicProp();
```
* 优点: 可以创建一个包含私有属性和私有方法的对象，很适合减少变量的污染
* 但是无法为私有成员无法创建单元测试。
  * 例子: 假如私有函数有bug，需要覆盖所有跟私有方法进行交互的公有方法。
* 无法轻易的扩展私有方法(书里介绍的，还有疑问，先留着)

* 跟揭示模式的区别，揭示模式的优点在于统一将公有方法和私有方法定义到函数体里面，然后私有函数可以调用公有函数，然后再返回对象中公开公有方法和属性，不过这样有很大的缺陷，私有函数假如能够调用公有函数，那么公有函数改变时要小心，因为可能会有私有函数会调用它，我不喜欢这样的模式，因为代码思路比较混乱，公有函数就是对外的，它只调用私有函数才对；私有函数没有必要调用公有函数，假如有需要那么就再创建一个私有函数，那么调用那个私有函数，如下代码
```
var myRevealingModule = (function() {
  var privateProp = 'pp1';
  function privateFunction() {
  }
  function publicFunction(a) {
    privateProp = a
  }
  return {
    publicFunction: publicFunction
  };
})();
```
