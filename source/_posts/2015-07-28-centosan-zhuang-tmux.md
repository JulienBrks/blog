---
title: 解决perl: warning: Setting locale failed
---
1、使用git下来源码
2、进入项目目录 `sh autogen.sh`
3、`make`
4、`sudo make install`

###### 遇到的问题:

* perl有提示"perl: warning: Setting locale failed"
解决方法如下：

>1、 Edit your user bash_profile

```
vi .bash_profile
```

>2、Insert the following:

```
export LANGUAGE=en_US.UTF-8

export LANG=en_US.UTF-8
export LC_ALL=en_US.UTF-8
```

>3、Rerun your Bash Profile

```
. ~/.bash_profile 
```
[参考链接](http://derrick-caluag.blogspot.com/2013/03/annoying-perl-warning-setting-locale.html)

* 遇到如下错误:
> tmux: error while loading shared libraries: libevent-2.0.so.5: cannot open shared object file: No such file or directory

解决办法:
`ln -s /usr/local/lib/libevent-2.0.so.5 /usr/lib/libevent-2.0.so.5`

[参考链接](http://www.nigeldunn.com/2011/12/11/libevent-2-0-so-5-cannot-open-shared-object-file-no-such-file-or-directory/)
