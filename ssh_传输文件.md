# ssh 传输文件

将本地文件拷贝到远程：  
scp + 文件名 + 用户名@计算机IP + ':' + 远程路径

```
scp testSerial.py ubuntu@10.42.0.1:~/
```

从远程将文件拷回本地：  
scp + 用户名@计算机IP + ':' + 文件名 + 本地路径

```
scp ubuntu@10.42.0.1:~/testSerial.py ~/
```