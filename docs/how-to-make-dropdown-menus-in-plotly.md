# 如何在 Plotly 中制作下拉菜单？

> 原文:[https://www . geeksforgeeks . org/如何制作下拉菜单-in-plotly/](https://www.geeksforgeeks.org/how-to-make-dropdown-menus-in-plotly/)

Plotly 是一个 Python 库，用于设计图形，尤其是交互式图形。它可以绘制各种图形和图表，如直方图、条形图、箱线图、展开图等。它主要用于数据分析以及财务分析。plotly 是一个交互式可视化库。

## 创建下拉菜单

下拉菜单是一直显示在屏幕上的菜单按钮的一部分。每个菜单按钮都与一个菜单部件相关联，该部件可以在单击该菜单按钮时显示该菜单按钮的选项。在 plotly 中，使用 updatemenu 方法修改图表有 4 种可能的方法。

*   **重新样式:**修改数据或数据属性
*   **重新布局:**修改布局属性
*   **更新:**修改数据和布局属性
*   **动画制作:**开始或暂停动画

**示例 1:** 重新样式下拉列表

可以修改图表的数据和数据属性。

## 蟒蛇 3

```py
import plotly.graph_objects as px
import numpy as np

# creating random data through randomint
# function of numpy.random
np.random.seed(42)

random_x = np.random.randint(1, 101, 100)
random_y = np.random.randint(1, 101, 100)

plot = px.Figure(data=[px.Scatter(
    x=random_x,
    y=random_y,
    mode='markers',)
])

# Add dropdown
plot.update_layout(
    updatemenus=[
        dict(
            buttons=list([
                dict(
                    args=["type", "scatter"],
                    label="Scatter Plot",
                    method="restyle"
                ),
                dict(
                    args=["type", "bar"],
                    label="Bar Chart",
                    method="restyle"
                )
            ]),
            direction="down",
        ),
    ]
)

plot.show()
```

**输出:**

<video class="wp-video-shortcode" id="video-486746-1" width="640" height="360" preload="metadata" controls=""><source type="video/webm" src="https://media.geeksforgeeks.org/wp-content/uploads/20200914223104/Screencast-from-Monday-14-September-2020-102951-IST.webm?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200914223104/Screencast-from-Monday-14-September-2020-102951-IST.webm](https://media.geeksforgeeks.org/wp-content/uploads/20200914223104/Screencast-from-Monday-14-September-2020-102951-IST.webm)</video>

**例 2:**

## 蟒蛇 3

```py
import plotly.graph_objects as px
import numpy

# creating random data through randomint
# function of numpy.random
np.random.seed(42)

random_x = np.random.randint(1, 101, 100)
random_y = np.random.randint(1, 101, 100)

x = ['A', 'B', 'C', 'D']

plot = px.Figure(data=[go.Bar(
    name='Data 1',
    x=x,
    y=[100, 200, 500, 673]
),
    go.Bar(
    name='Data 2',
    x=x,
    y=[56, 123, 982, 213]
)
])

# Add dropdown
plot.update_layout(
    updatemenus=[
        dict(
            active=0,
            buttons=list([
                dict(label="Both",
                     method="update",
                     args=[{"visible": [True, True]},
                           {"title": "Both"}]),
                dict(label="Data 1",
                     method="update",
                     args=[{"visible": [True, False]},
                           {"title": "Data 1",
                            }]),
                dict(label="Data 2",
                     method="update",
                     args=[{"visible": [False, True]},
                           {"title": "Data 2",
                            }]),
            ]),
        )
    ])

plot.show()
```

**输出:**

<video class="wp-video-shortcode" id="video-486746-2" width="640" height="360" preload="metadata" controls=""><source type="video/webm" src="https://media.geeksforgeeks.org/wp-content/uploads/20200914223202/Screencast-from-Monday-14-September-2020-103115-IST.webm?_=2">[https://media.geeksforgeeks.org/wp-content/uploads/20200914223202/Screencast-from-Monday-14-September-2020-103115-IST.webm](https://media.geeksforgeeks.org/wp-content/uploads/20200914223202/Screencast-from-Monday-14-September-2020-103115-IST.webm)</video>