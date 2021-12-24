# 如何在 Plotly 中制作滑块？

> 原文:[https://www . geeksforgeeks . org/how-to-make-sliders-in-plot/](https://www.geeksforgeeks.org/how-to-make-sliders-in-plotly/)

Plotly 是一个 Python 库，用于设计图形，尤其是交互式图形。它可以绘制各种图形和图表，如直方图、条形图、箱线图、展开图等。它主要用于数据分析以及财务分析。plotly 是一个交互式可视化库。

## 简单滑块控件

一般来说，滑块是一个 Tkit 对象，用户可以通过移动指示器来设置值。滑块可以垂直和水平排列。在图中，滑块可以通过使用比例方法()形成。

**例 1:**

## 蟒蛇 3

```
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

<video class="wp-video-shortcode" id="video-490372-1" width="640" height="360" preload="metadata" controls=""><source type="video/webm" src="https://media.geeksforgeeks.org/wp-content/uploads/20200914210651/Screencast-from-Monday-14-September-2020-090335-IST.webm?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200914210651/Screencast-from-Monday-14-September-2020-090335-IST.webm](https://media.geeksforgeeks.org/wp-content/uploads/20200914210651/Screencast-from-Monday-14-September-2020-090335-IST.webm)</video>

**例 2:**

## 蟒蛇 3

```
import plotly.express as px

df = px.data.tips()

fig = px.scatter(df, x="total_bill", y="tip", 
                 animation_frame="day",
                 color="sex",)

fig["layout"].pop("updatemenus")
fig.show()
```

**输出:**

<video class="wp-video-shortcode" id="video-490372-2" width="640" height="360" preload="metadata" controls=""><source type="video/webm" src="https://media.geeksforgeeks.org/wp-content/uploads/20200922210907/Screencast-from-Tuesday-22-September-2020-090816-IST.webm?_=2">[https://media.geeksforgeeks.org/wp-content/uploads/20200922210907/Screencast-from-Tuesday-22-September-2020-090816-IST.webm](https://media.geeksforgeeks.org/wp-content/uploads/20200922210907/Screencast-from-Tuesday-22-September-2020-090816-IST.webm)</video>