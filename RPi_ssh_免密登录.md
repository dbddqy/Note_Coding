# RPi ssh 免密登录

创建密钥， 一路回车：  

```
ssh-keygen
```

然后， 一路yes：  

```
ssh-copy-id -f -i .ssh/id_rsa.pub ubuntu@192.168.179.113
```

注意之后免密登录不需要sudo，不然还是要密码