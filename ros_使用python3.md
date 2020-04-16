# ros 使用python3

ros中的python节点可以使用python3解释器，相应的python脚本需要在开头注明

```py
#!/usr/bin/env python3
```

此外直接import rospy时会出现error，需要安装

```
pip install catkin-tools
pip install rospkg
```
