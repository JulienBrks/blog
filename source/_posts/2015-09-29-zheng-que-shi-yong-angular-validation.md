---
title: 正确使用angular的config方法
---
1、基本用法: 定义模块的config阶段进行声明需要绑定的验证关系，代码如下:
```
angular.module 'network_manage', ['validation']
.config ($validationProvider) ->
  $validationProvider.setErrorHTML (msg) ->
    return "<small class='error'>" + msg + "</small>"

  required = (value) ->
    return !!value

  expression =
    requiredName: required
    requiredAddress: required

  messages =
    requiredName:
      error: '网点姓名不能为空'
    requiredAddress:
      error: '请输入地址'

  $validationProvider.setExpression expression
    .setDefaultMsg messages

```

2、假如需要更改默认的验证方式的话，可以在需要验证的元素中加上一个`valid-method`属性, 它的取值有`submit`, `blur`分别表示什么时候验证，blur表示失去焦点验证，submit表示提交的时候验证。
3、假如是form表单，某一个输入框回车的时候，它会选择第一个没有设置`type=button`的按钮，所以假如提交的按钮在最后，那么前面的按钮一定要加上`type=button`.
4、假如不想给某一个输入款回车就提交，可以绑定ng-click然后使用`$event.preventDefault()`。
5、假如要在submit的时候能够验证, 那么必须为input加上name属性
