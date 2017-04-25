原因: 由于跨域请求的两个域的session cookie是不一样的，所以我们发起一个跨域请求时，本域的session cookie不会放到跨域请求的Set-Cookie头里面。

可以通过参数增加xhrFields字段解决这个问题
```
$.ajax({
   url: a_cross_domain_url,
   xhrFields: {
      withCredentials: true
   }
});
```
但是这样有一个问题，那么就是服务端不能够设置   'Access-Control-Allow-Origin': '*', 必须指定某些域才行。

PS: 假如这个域自己能够管理的，那么就使用反向代理到同一个域下面，但是这样往往不好。所以跨域请求就不要使用session cookie的，因为http本身就是一个无状态的协议，而session cookie是上一个时代服务器session遗留的产物，就不用使用啦，可以通过token能方式进行认证交互啦。
