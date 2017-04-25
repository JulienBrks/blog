#### 作用:
它主要使用在typescript的编译中作为配置文件，typescript的编译会默认寻找当前目录的tsconfig.json，然后读取里面的配置进行编译。

#### 主要选项

* `files`，它的值是一个字符串数组。用来规定要被编译的文件, 假如需要编译某一个文件，那么就应该将这个文件放入到里面。如下
```
{
  "compilerOptions": {
    "target": "es5",
    "module": "commonjs"
  },
  "files": [            "src/app/account/information/controllers/information.controller.ts",
]
```
* `compilerOptions`, 它配置typescript编译的一些要求，比如要求编译成es5，编译之后是commonjs的语法等。

#### atom-typescript支持的选项
* `filesGrob`和`atom: {"rewriteTsconfig": true}`: 它可以使用`glob / minimatch / RegExp`等方式进行匹配, 然后支持将所有的符合条件的文件放到`files`的数组里面。下面这张图片可以看出，files数组里面存放所有符合filesGlob的`src/app/**/*.ts`条件的文件。
![自动扩展图片实例](/content/images/2015/11/a-2.png)


#### 我的配置
```
{
  "compilerOptions": {
    "target": "es5",
    "module": "commonjs"
  },
  "filesGlob": [
    "src/app/**/*.ts"
  ],
  "atom": {
    "rewriteTsconfig": true
  },
  "files": [
    "src/app/index.module.ts",
    "src/app/account/information/interfaces/information.ts"
  ]
}

```