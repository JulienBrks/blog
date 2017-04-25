首先我们来看下文件夹的作用，将一批文件作为一个最小单位进行操作，它的主要功效是让批量操作变得非常简单。但是深层次的文件夹使阅读非常不方便，这个可以通过优化文件夹的创建方式解决这个问题。

在一个前端项目中，其实最需要做的是组件化，不断细化最小组件，充分复用。当然对于大项目来讲的话，还有一个层次就是业务模块。最后一点就是整个项目的开发层次划分，对于angular的项目，一般存在filter, directive和service等分层。那么如何根据这些进行合理的分层呢？

我觉得以可视化页面层级进行分文件夹会更好，然后将某一个视图下面需要的coffee直接挂到那个视图下面, 对于js,我觉得就按照上面的规则进行判断是否创建文件夹就好了。

* 按照模块进行分层:我觉得对于一个比较大型的项目来讲的话，我觉得能够将整个项目按照业务模块来分是非常有必要的。主要是能够保证每一个业务模块都是独立的，能够保证业务模块能够进行非常容易的迁移(或者重命名,或者删除)。那么如何处理一个单独的视图(页面)呢？我认为也是给专门的文件夹会好一点，理由跟上面类似。
* 将filter, service, template,directive分离是较好的。因为相较于将js放到一个文件，分离方便我们找到相对应的功能文件。那么要不要给专门的文件夹呢？我认为没有必要的, 因为假如我们的视图能够足够原子化，能够自给自足的话,filter,service这些功能模块的划分不符合文件夹的好处, 那就是不符合能够批量删除,修改和重命名的好处。
* 但是对于img, css的静态资源文件, 我觉得还是要创建一个img文件夹, css文件夹(也可以命名为less, scss或者sass)作为静态资源存放的地方，但是img下面就不要再创建文件夹了，因为一个视图所需要的图片就是一个集合。
* 关于sprite, 我的建议是创建一个sprite文件夹, 作为等待合并的小图标
* src作为源代码文件, dist作为可以运行的文件夹
* 对于公用的组件库, 我的建议是放到src文件夹下面作为"子模块"引入，因为它也会被编译到dist下面，所以保证src和dist是一个生成关系比较清晰。
* 代码抽象。这样的目录结构根据模块到视图这样的层次递进，子层相当于父层的儿子，可以访问父层的共有"方法", 公有"属性", 比如user模块的filter, 可以引入common模块的filter作为基类继承。作为统一目录的两个文件夹里面的js不应该存在依赖关系。比如user-list-sidebar里面的模块不能依赖user-list-content里面的模块, 假如要存在依赖管理，那么就提取出公用的部分, 放到上一级目录进行依赖。
* 关于组件,ui里面的内容。ui里面的内容按照组件分割,其实内容跟模块和视图的概念是一样的啦，为每一个组件创建一个文件夹。

* app/ // 项目目录
  * src/
    * ui/
      * src/
        * common
          * css/
          * js/
        * pagination/
          css/
          js/
    * common/
    * user/ // 用户模块
      * user-list/ // 用户列表视图
        * filter.coffee
        * index.jade
        * img/
        * sprite/
        * scss/
        * user-list-sidebar/ // 用户列表左边的子视图
          * index.jade
          * filter.coffee
          * service.coffee
        * user-list-content/
          * index.jade
          * filter.coffee
          * service.coffee 
   * dist/
    * user/ // 用户模块
      * user-list/ // 用户列表视图
        * filter.coffee
        * index.jade
        * img/
        * sprite.png
        * scss/
        * user-list-sidebar/ // 用户列表左边的子视图
          * index.jade
          * filter.coffee
          * service.coffee
        * user-list-content/
          * index.jade
          * filter.coffee
          * service.coffee 