# opencv 遍历图像

最高效的方法是使用指针遍历图像

```cpp
for (int v = 0; v < matDepth.rows; ++v) {
    for (int u = 0; u < matDepth.cols; ++u) {
        uint16_t d = matDepth.ptr<uint16_t>(v)[u];
    }
}
```

例子中遍历深度图像并获取其深度值（16位int）  

## **注意:**

**uv**的位置很容易弄反  
**u**为行坐标（列号），**v**为列坐标（行号）  
因此在三维重建时：  

$$
\left\{
\begin{aligned}
& x = (u - cx) * d / fx \\
& y = (v - cy) * d / fy \\
& z = d
\end{aligned}
\right.
$$

代码：

```cpp
pcl::PointXYZ point((u-cx)*d/fx, (v-cy)*d/fy, d);
```