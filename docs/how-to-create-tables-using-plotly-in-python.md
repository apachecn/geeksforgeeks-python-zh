# 如何在 Python 中使用 Plotly 创建表格？

> 原文:[https://www . geeksforgeeks . org/如何使用 python 中的 plotly 创建表格/](https://www.geeksforgeeks.org/how-to-create-tables-using-plotly-in-python/)

[Plotly](https://www.geeksforgeeks.org/getting-started-with-plotly-python/) 是一个 Python 库，用来设计图形，尤其是交互图形。它可以绘制各种图形和图表，如直方图、条形图、箱线图、展开图等。它主要用于数据分析以及财务分析。plotly 是一个交互式可视化库。

## Plotly 中的表格

表格有助于将数据组织成列和行。表格的使用在所有的交流、研究和数据分析中都很普遍。他们喜欢信息的快速输入和成比例的基本比较。可以使用 **graph_objects** 类的 **Table()** 方法创建。

> **语法:** plotly.graph_objects。表格(参数=无，单元格=无，列顺序=无，列宽度=无，标题=无，**kwargs)
> 
> **参数:**
> 
> **arg:** 与此构造函数或 plotly.graph_objects 实例兼容的属性集合。桌子
> 
> **单元格:**plot . graph _ objects . table .具有兼容属性的单元格实例或 dict
> 
> **列顺序:**指定数据列的渲染顺序；例如，位置 0 处的值 2 意味着数据中的列索引 0 将呈现为第三列，因为列的索引基数为零。
> 
> **列宽:**以比例表示的列宽。列按照其指定列宽的比例填充可用宽度。
> 
> **标题:**plot . graph _ objects . table .具有兼容属性的标题实例或 dict

**示例:**

## 蟒蛇 3

```py
import plotly.graph_objects as go

fig = go.Figure(data=[go.Table(
    header=dict(values=['A', 'B']),
    cells=dict(values=[[10, 20, 30, 40],
                       [40, 20, 10, 50]]))
])
fig.show()
```