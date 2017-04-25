* parseInt([12, 13]) === 12 这个表达式成立，不够严谨
* js存在声明提升，所以在函数作用域内，尽管声明语句在最后，它也会在编译的时候放到函数最前面声明，相当于优先执行`var a;`
* 同一个标识符的情况下，变量声明与函数声明都会提升；函数声明会覆盖变量声明，但不会覆盖变量赋值，即：如果声明变量的同时初始化或赋值那么变量优先级高于函数。