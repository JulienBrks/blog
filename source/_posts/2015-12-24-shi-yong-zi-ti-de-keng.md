今天想打印一个页面，这个页面是批量生成的，发现每一次打印都无法打印字体，我还以为是浏览器渲染比较慢导致的。后来查询了很多浏览器的事件触发机制，发现始终会有这样的问题。后来我想到便利每一个元素的文字内容，只有等待文字内容全部被渲染完毕之后再触发print()。但是发现还是不成功，发现页面很快就出现了打印弹窗，然后发现其实文字已经被加入到dom结构里面了。然后我才开始怀疑是字体的问题，果然，我不使用外部字体就解决了这个问题。

我发现打印似乎会等待页面内容渲染完之后再进行打印，当然它不会等待外部字体的渲染。