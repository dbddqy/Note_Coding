# ros_有线连接xbox_one手柄

首先安装ros中的joy包
```
sudo apt-get install ros-kinetic-joy
```

---

插上手柄，查看设备
```
ls /dev/input/
```

出现类似以下信息：
```
by-id    event0  event2  event4  event6  event8  mouse0  mouse2  uinput
by-path  event1  event3  event5  event7  js0     mice    mouse1
```

有jsX就说明连上了，可以用该命令测试手柄：
```
sudo jstest /dev/input/js0
```

---

查看权限：
```
ls -l /dev/input/js0
```

出现类似以下信息：
```
crw-rw-XX- 1 root dialout 188, 0 2009-08-14 12:04 /dev/input/jsX
```

其中的XX需要是rw，不是的话，更改其权限：
```
sudo chmod a+rw /dev/input/js0
```

---

启动roscore，加载参数（设备名），启动joy节点
```
roscore
rosparam set joy_node/dev "/dev/input/js0"
rosrun joy joy_node
```

订阅节点
```
rostopic echo joy
```

---

xbox one 手柄按键对应关系

| axes | - | buttons（按下1，不按0） |
| :---: | :---: | :---: |
| 0 | 左遥杆（←：1.0 →：-1.0） | A | 
| 1 | 左遥杆（↑：1.0 ↓：-1.0） | B | 
| 2 | LT（不按：1.0 按下：-1.0） | X |
| 3 | 右遥杆（←：1.0 →：-1.0） | Y |
| 4 | 右遥杆（↑：1.0 ↓：-1.0） | LB |
| 5 | LR（不按：1.0 按下：-1.0） | RB |
| 6 | 左按键（←：1.0 →：-1.0） | 左小按钮 |
| 7 | 左按键（↑：1.0 ↓：-1.0） | 右小按钮 |
| 8 | - | - |
| 9 | - | 左遥杆 |
| 10 | - | 右遥杆 |