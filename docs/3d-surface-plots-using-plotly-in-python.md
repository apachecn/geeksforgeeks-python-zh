# 使用 Python 中的 Plotly 绘制三维曲面图

> 原文:[https://www . geesforgeks . org/3d-surface-plots-use-plotly-in-python/](https://www.geeksforgeeks.org/3d-surface-plots-using-plotly-in-python/)

[Plotly](https://www.geeksforgeeks.org/getting-started-with-plotly-python/) 是一个 Python 库，用来设计图形，尤其是交互图形。它可以绘制各种图形和图表，如直方图、条形图、箱线图、展开图等。它主要用于数据分析以及财务分析。plotly 是一个交互式可视化库。

## 绘制表面图

表面图是那些具有三维数据的图，这些三维数据是 X，Y 和 z。表面图不是显示单个数据点，而是在因变量 Y 之间具有函数关系，并且具有两个自变量 X 和 z。该图用于区分因变量和自变量。

> **语法:** plotly.graph_objects。曲面(参数=无，悬停信息=无，x =无，y =无，z =无，**kwargs)
> 
> **参数:**
> 
> **arg:** 与此构造函数或 plotly.graph_objects 实例兼容的属性集合。表面
> 
> **x:** 设置 x 坐标。
> 
> **y:** 设置 y 坐标。
> 
> **z:** 设置 z 坐标。
> 
> **悬停信息:**确定悬停时出现哪些跟踪信息。如果设置了无或跳过，悬停时不会显示任何信息。但是，如果没有设置，点击和悬停事件仍然会触发。

**示例:**

## 蟒蛇 3

```py
import plotly.graph_objects as go
import numpy as np

x = np.outer(np.linspace(-2, 2, 30), np.ones(30))
y = x.copy().T
z = np.cos(x ** 2 + y ** 2)

fig = go.Figure(data=[go.Surface(x=x, y=y, z=z)])

fig.show()
```