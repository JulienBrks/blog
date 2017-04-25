* 思路一:使用chrome的私有属性设置特殊的背景和字体颜色
```
input:-webkit-autofill {
  -webkit-box-shadow: 0 0 0px 1000px white inset;
  -webkit-text-fill-color: #333;
}
```
* 思路二:关闭自动填充功能，设置表单属性 autocomplete="off/on" 关闭自动填充表单，自己实现记住密码
```
<!-- 对整个表单设置 -->
<form autocomplete="off" method=".." action="..">
<!-- 或对单一元素设置 -->
<input type="text" name="textboxname" autocomplete="off">
```