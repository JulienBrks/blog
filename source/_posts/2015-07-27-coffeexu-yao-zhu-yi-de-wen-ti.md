* `if not a`跟 `if not a?`不一样，假如我们要判断a为null或者undefined的时候使用`if not a?`更确切。`if not a`假如a为0的时候会判断成立。
* `not`的优先级比`and`，所以在`if`语句中使用`not`要使用括号括起来才行。