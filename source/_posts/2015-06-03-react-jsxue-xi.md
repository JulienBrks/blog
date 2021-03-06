---
title: angularjs跟reactjs区别
---
今天主要讲下reactjs和angularjs的区别:

1. react提供了一个创建组件所需的行为和模板，它使用createClass这个方法创建一个组件,使用render方法返回一个模板，使用getInitialState方法初始化state(状态),这个状态保存了模板所需要的数据(模型)。在angularjs里面也同样存在指令完成了同样的功能, 两者都有模板定义,都可以申明模型,都可以创建模板上的行为, 区别不是很大。
2. 双向绑定和单向绑定。reactjs使用了单向绑定的策略，而不像angularjs的双向绑定，这样的一个区别是视图数据和模型数据是否一致，或者说是否需要用户主动指定数据变更。其实我觉得angularjs的双向为用户提供了极大的便利。
3. 模型状态。reactjs包含的数据有多个state(状态)为了满足一个组件拥有的多个状态。相比与angularjs里面, 只有一个$scope作用域不同，它多加了数据状态的特性，而这个特性确实很多使用我们需要的。再angularjs里面，我们需要保存数据修改前和修改后的两份状态副本，但是reactjs自动帮我们做到了状态变更的管理，我们可以更好地进行切换状态，这个过程我们需要框架帮我们隐藏，只是提供了接口就行了，提供了我们对于个数据状态管理的一套切实可行的解决方案。
4. 由angularjs过渡到reactjs的学习上，其实最大的区别是reactjs独特的jsx语法，除此之外，其余差别不多，不过jsx语法也不难。感觉react的学习成本比angular学习成本要低，angularjs的指令定义了很多配置，让我们使用，但是配置需要学习api，而react则更像javascript，它创建的组件就是一个公用方法的组合，一些配置方面的内容，融入到了代码里面，用户自定义程度更高，我觉得这就是大家逐渐用gulp代替grunt的原因把。提供了配置本身就限制了可能性，而且增加了对于配置的学习，而gulp只提供了几个流处理方法，每一个任务的创建都是一个个不同的流处理方式，不需要学习大量的配置参数，而且定制能够太弱。
