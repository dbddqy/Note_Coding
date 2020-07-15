# RPi Ubuntu Mate Wifi配置

下镜像，烧sd卡，... ，然后发现wifi不能用

### 配置wifi

进入/etc/network/目录中，编辑interfaces文件

原文件：
>\# interfaces(5) file used by ifup(8) and ifdown(8)  
 \# Include files from /etc/network/interfaces.d:  
 source-directory /etc/network/interfaces.d  
 \# The loopback network interface  
 auto lo  
 iface lo inet loopback

在后面加入

>auto wlan0  
 iface wlan0 inet dhcp  
 pre-up wpa_supplicant -Dwext -i wlan0 -c /ect/wpa_supplicant/wpa_supplicant.conf -B

 进入/etc/wpa_supplicant，新建一个名为wpa_supplicant.conf的文件，内容为

 >network={  
       ssid="xxx"  
        psk="xxx"  
}

ssid和psk分别对应无线网名称和密码

然后重启，注释掉/etc/network/interfaces 中的新加内容，再重启，应该就能连上网络了。

### 安装并启动 openssh

```
sudo apt update
sudo apt install openssh-server
sudo /etc/init.d/ssh start
```

### 无显示器启动

打开boot/config.txt文件，在其中加入

> hdmi_force_hotplug=1