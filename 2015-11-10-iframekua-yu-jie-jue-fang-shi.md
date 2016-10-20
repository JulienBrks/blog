首先angular默认不支持iframe访问其他域名，因为它认为这种方式是不安全的。但是它提供了一种方式可以让我们访问:`var url = $sce.trustAsResourceUrl(url)`, 将其他域名的url放到这个方法里面，然后让iframe的src为这个方法的返回值`<iframe src="{{url}}"></iframe>`，这样就能够打开这个iframe了。

更进一步，假如我们需要访问到这个iframe里面的元素的话，我们发现还是不行，由于
![两个域名不一样](/content/images/2015/11/a.png)，导致还是不能访问到里面的内容。网上搜索到可以使用jsonp的方式完成访问里面页面的内容，但是比较麻烦。所以为了让两个域名一样，还是老老实实使用dns解析把，让父iframe的域名和子iframe的域名改成一样的域名，这样就可以完成父iframe可以操作子iframe的内容了。

