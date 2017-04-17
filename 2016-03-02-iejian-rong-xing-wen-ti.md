1. IE6和IE7不支持box-sizing, table-cell
2. 使用table-cell进行垂直居中的时候发现IE7下不能够成功，通过一些hack属性可以完美支持IE7和IE6，具体请看[链接](http://bbs.blueidea.com/thread-2823535-1-1.html).
3. IE5及以下或者IE下的混淆模式会出现盒模型(我们称之为IE盒模型)跟w3c定义的盒模型不一样，IE的盒模型的width(或者height)=content的总宽度 + padding的总宽度 + border的总宽度。而w3c的盒模型为width = content的总宽度。
4. 我们可以通过`box-sizing`来设置元素width包含的内容，但是对于IE浏览器，IE8及以上才支持这个属性。
5. IE6不支持属性选择器，如`[disabled=disabled]`
6. IE8不支持`:disabled`伪类，假如跟其他类一起使用的话，那么也会导致那个类也会有问题。所以为了兼容IE8，不推荐使用`:disabled`伪类。
7. IE和chrome浏览器有时候background-color呈现的颜色不一样，应该是IE会存在有一些颜色渲染不了。如[链接](https://social.msdn.microsoft.com/Forums/ie/en-US/6757da6e-5aa4-4219-8c31-c3dfc992c6eb/ie-does-not-render-images-the-correct-color?forum=iewebdevelopment)。
8. IE7及以下不支持:after和:before伪类
9. IE8及以下不支持使用`overflow: auto;`来修复margin的塌陷。
10. 使用new Date传入日期字符串的话，为了兼容低版本的IE和低版本的firefox，日期字符串使用"2012/03/28"替代"2012-03-28"格式。
11. 两个同级的div，一个设置成`position: absolute;`，另外一个`position: static;`，相同的zindex, 在IE下认为`position: aboslute;`的元素显示层级会高一点；在chrome下则按照元素的排列顺序显示层级，后面的元素显示的层级高一点。 不过IE下面假如想`让position:static`的元素显示在同级设置为`position:absolute/relative`的元素上面，仅仅使用zindex没有用，还需要设置为`position:absolute/relative`。建议写法: 有层级关系的明确使用使用z-index区分，然后想要让不设置为position: static的元素显示在前面，那么就将这个元素设置成`position: relative`。
12. IE8不支持bind方法，为了兼容IE8，可以使用`$.proxy()`方法代替。
13. IE8混乱模式，IE7混乱模式，不支持子选择器和相邻选择器。
14. IE8支持的css文件个数有限制
15. IE11及以下对font-famliy的值的字符长度有限制，最大32位
