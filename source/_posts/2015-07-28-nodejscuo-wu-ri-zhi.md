1、回调函数的错误回调函数应该要传，然后对错误使用deferred.reject返回,这样对于后期解决bug有很大的帮助。
2、可以在全局捕获程序中未捕获的错误，然后打印日志