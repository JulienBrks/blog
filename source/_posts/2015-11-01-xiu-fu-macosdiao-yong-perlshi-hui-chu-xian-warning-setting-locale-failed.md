---
title: 修复恼人的 perl warning Setting locale failed
---
### 
```
perl: warning: Setting locale failed.
perl: warning: Please check that your locale settings:
     LC_ALL = "En_US",
     LANG = (unset)
are supported and installed on your system.
perl: warning: Falling back to the standard locale ("C").
```
只有在~/.zshrc, ~/.bashrc, ~/.cshrc文件后面增加下面几句话就好了:
```
# This setting is for the new UTF-8 terminal support
export LC_CTYPE=en_US.UTF-8
export LC_ALL=en_US.UTF-8
```

以上所述方法来自[链接](http://blogs.law.harvard.edu/hoanga/2008/04/10/fixing-that-really-irritating-perl-warning-setting-locale-failed-on/)
