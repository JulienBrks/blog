---
title: 如何清除chrome的dns缓存
---
需要使用gas mask切换本地hosts文件来达到开发环境的切换，但是今天发现这个切换在chrome浏览器中没有生效。从hosts1切换到hosts2的时候, 发现chrome还是使用hosts1的配置，然后在shell中ping却发现是hosts2的配置。所以我就感觉是chrome这边存在dns缓存，通过google之后发现其他人确实也存在跟我一样的[问题](http://superuser.com/questions/203674/how-to-clear-flush-the-dns-cache-in-google-chrome)。

我按照里面的最佳答案使用chrome打开`chrome://net-internals/#dns`，清除dns缓存之后发现还是没有起作用。于是我继续这个答案下面的其他人的评论后发现其他人也遇到这样的问题，就是host1的配置是外部ip，host2的配置的127.0.0.1，发现切换到host2的配置之后，dns解析到的还是host1里面的外部ip。然后偶然看到第二个答案写着`Sometimes you need to flush the socket pools after flushing the DNS:`，我也尝试了他提供的答案打开`chrome://net-internals/#sockets`，然后点击清楚sokects缓存。于是世界又恢复正常了，又可以愉快的跟chrome和平共处了:)
