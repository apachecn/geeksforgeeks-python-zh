# 如何在 Plotly 中制作范围滑块和选择器？

> 原文:[https://www . geeksforgeeks . org/如何制作范围滑块和选择器绘图/](https://www.geeksforgeeks.org/how-to-make-range-slider-and-selector-in-plotly/)

Plotly 是一个 Python 库，用于设计图形，尤其是交互式图形。它可以绘制各种图形和图表，如直方图、条形图、箱线图、展开图等。它主要用于数据分析以及财务分析。plotly 是一个交互式可视化库。

## 创建范围滑块和选择器

在 plotly 中，范围滑块是一个自定义范围类型的输入控件。它允许在指定的最小和最大范围之间选择一个值或一系列值。范围选择器是一个选择图表中显示的范围的工具。它提供了在图表中选择预配置范围的按钮。它还提供了输入框，可以手动输入最小和最大日期。

**示例:**

## 蟒蛇 3

```py
import plotly.graph_objects as px
import plotly.express as go
import numpy as np

df = go.data.tips()

x = df['total_bill']
y = df['day']

plot = px.Figure(data=[px.Scatter(
    x=x,
    y=y,
    mode='lines',)
])

plot.update_layout(
    xaxis=dict(
        rangeselector=dict(
            buttons=list([
                dict(count=1,
                     step="day",
                     stepmode="backward"),
            ])
        ),
        rangeslider=dict(
            visible=True
        ),
    )
)

plot.show()
```

**输出:**

<video class="wp-video-shortcode" id="video-486799-1" width="640" height="360" preload="metadata" controls=""><source type="video/webm" src="https://media.geeksforgeeks.org/wp-content/uploads/20200914210651/Screencast-from-Monday-14-September-2020-090335-IST.webm?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200914210651/Screencast-from-Monday-14-September-2020-090335-IST.webm](https://media.geeksforgeeks.org/wp-content/uploads/20200914210651/Screencast-from-Monday-14-September-2020-090335-IST.webm)</video>