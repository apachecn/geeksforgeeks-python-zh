# 使用 Python 中的 Plotly 绘制三维网格图

> 原文:[https://www . geesforgeks . org/3d-mesh-plots-use-plotly-in-python/](https://www.geeksforgeeks.org/3d-mesh-plots-using-plotly-in-python/)

Plotly 是一个 Python 库，用于设计图形，尤其是交互式图形。它可以绘制各种图形和图表，如直方图、条形图、箱线图、展开图等。它主要用于数据分析以及财务分析。plotly 是一个交互式可视化库

## 三维网格图

网格图是一种具有三维曲面、实心边且没有面颜色的图。网格图是一种创建三维三角形集的方法，三角形的顶点由 x、y 和 z 给出。如果只有坐标，则使用德劳奈三角剖分等算法来形成三角形。I、J 和 K 参数也可以用来创建三角形。

> **语法:【plotly.graph _ objects 类。网格 3d(参数=无，悬停信息=无，x =无，y =无，z =无，**kwargs)**
> 
> **参数:**
> 
> **arg:** 与此构造函数或 plotly.graph_objects 实例兼容的属性集合。网格 3d
> 
> **悬停信息:**确定悬停时出现哪些跟踪信息。如果设置了无或跳过，悬停时不会显示任何信息。但是，如果没有设置，点击和悬停事件仍然会触发。
> 
> **x:** 设置顶点的 X 坐标。向量 X、Y 和 Z 的第 n 个元素共同表示第 n 个顶点的 X、Y 和 Z 坐标。
> 
> **y:** 设置顶点的 Y 坐标。向量 X、Y 和 Z 的第 n 个元素共同表示第 n 个顶点的 X、Y 和 Z 坐标。
> 
> **z:** 设置顶点的 Z 坐标。向量 X、Y 和 Z 的第 n 个元素共同表示第 n 个顶点的 X、Y 和 Z 坐标。

**例 1:**

## 蟒蛇 3

```
import plotly.graph_objects as go
import numpy as np

# Data for three-dimensional scattered points
z = 15 * np.random.random(100)
x = np.sin(z) + 0.1 * np.random.randn(100)
y = np.cos(z) + 0.1 * np.random.randn(100)

fig = go.Figure(data=[go.Mesh3d(
  x=x, y=y, z=z, color='green', opacity=0.20)])

fig.show()
```