# 使用 Python Plotly 绘制地毯图

> 原文:[https://www . geeksforgeeks . org/地毯图-使用 python 中的 plotly/](https://www.geeksforgeeks.org/carpet-plots-using-plotly-in-python/)

Plotly 是一个 Python 库，用于设计图形，尤其是交互式图形。它可以绘制各种图形和图表，如直方图、条形图、箱线图、展开图等。它主要用于数据分析以及财务分析。Plotly 是一个交互式可视化库。

## 地毯图

地毯图是几种不同的特定类型的图中的任何一种。地毯图是显示二维图中两个或多个自变量和一个或多个因变量之间相互作用的图。地毯图有别于其他图，因为地毯图可用于更精确地插值数据点。可以使用 graph_objects 类的**地毯()**方法创建。

> **语法:** plotly.graph_objects。地毯(a =无，b =无，地毯=无，x =无，y =无)
> 
> **参数:**
> 
> **a:** 包含第一个参数值的数组
> 
> **b:** 包含第一个参数值的数组
> 
> **x:** 每个地毯点的 x 坐标的二维数组。如果省略，则该阴谋是骗子阴谋，默认情况下 xaxis 是隐藏的。
> 
> **y:** 每个地毯点的 y 坐标的二维数组。
> 
> **地毯:**该地毯的标识符，以便散点地毯和连续地毯轨迹可以指定它们所在的地毯区域

**示例:**

## 蟒蛇 3

```py
import plotly.graph_objects as go

fig = go.Figure(go.Carpet(
    y = [1, 2, 3, 4, 5, 6]
))

fig.show()
```