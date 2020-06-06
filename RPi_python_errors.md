# RPi python errors

使用pip安装软件时出现error：locale.Error: unsupported locale setting  

解决：
```
export LC_ALL=C
```