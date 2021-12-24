# Python 中使用 Plotly 的极坐标图

> 原文:[https://www . geesforgeks . org/polar-charts-use-plotly-in-python/](https://www.geeksforgeeks.org/polar-charts-using-plotly-in-python/)

Plotly 是一个 Python 库，用于设计图形，尤其是交互式图形。它可以绘制各种图形和图表，如直方图、条形图、箱线图、展开图等。它主要用于数据分析以及财务分析。plotly 是一个交互式可视化库。

## Plotly 中的极坐标图

这些图表使用极坐标系统，其 x 轴看起来像一个以原点为中心的圆，每个点都由与固定点的距离和与固定方向的角度决定。极坐标图也被称为雷达图、网络图、蜘蛛图和星图等。径向坐标和角度坐标名称作为 r 和θ参数给出。

> **语法:** plotly.graph_objects。散点图(arg =无，cliponaxis =无，dr =无，dtheta =无，line =无，marker =无，r =无，theta =无)
> 
> **参数:**
> 
> **arg:** 与此构造函数或 plotly.graph_objects 实例兼容的属性集合。散射极
> 
> **r:** 设置径向坐标
> 
> **θ:**设置径向坐标
> 
> **线:**具有兼容属性的 plotly.graph _ .散点图. line 实例或 dict
> 
> **标记:** plotly.graph_objects .散点图.具有兼容属性的标记实例或 dict

**示例:**

## 蟒蛇 3

```py
import plotly.graph_objects as go

fig = go.Figure(data=go.Scatterpolar(
    r=[1, 2, 3, 4, 5, 6, 7, 8, 9],
    theta=[69, 141, 213, 285, 357,
           429, 501, 573, 645],
    mode='markers',
))

fig.show()
```