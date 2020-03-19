# opencv 打开16位深度图像
使用opencv读取rgb图像与深度图像进行3维重建， 发现点云信息不正确。
原因是16位的深度图像没有以正确的方式读取。
```cpp
Mat matDepth = imread((boost::format("../data2D/depth_%d.png") % frame_index).str(), CV_LOAD_IMAGE_UNCHANGED);
```
其中的 **CV_LOAD_IMAGE_UNCHANGED** 一定要加上