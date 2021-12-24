# 使用 Python 中的牛郎星突出显示条形图中的一个条形

> 原文:[https://www . geesforgeks . org/highlight-a-bar-in-bar-chart-use-Altair-in-python/](https://www.geeksforgeeks.org/highlight-a-bar-in-bar-chart-using-altair-in-python/)

数据可视化是数据的图形化表示，Python 附带了几个可以用于数据可视化的库，这使得它成为数据科学家的热门选择。牛郎星就是 Python 中的一个这样的数据可视化库。Altair API 简单、用户友好、一致，构建在 Vega-Lite JSON 配置之上。

在本文中，我们使用了 Altair 来创建数据集的条形图，并突出显示符合指定条件的条形图。使用的另一个图书馆是熊猫。Pandas 是 Python 中的数据分析库，可用于数据集的操作。

要使用*牛郎星*从给定数据集创建条形图，需要使用*牛郎星*模块的*图表*类。

**句法:**

> **牛郎星。图表(**数据、编码、标记、宽度、高度、**kwargs **)**
> 
> **参数:**
> 
> *   **Data:** This refers to the data set.
> *   **Code:** It is the key-value mapping between the code channel and the field definition.
> *   **Mark:** Specify the type of mark, that is, bar, circle, square, area, point, etc.
> *   **Width:** Specify the visualization width.
> *   **Height:** Specify the visualization width.
> 
> **注:** **kwargs:允许传递可变长度参数

让我们考虑以下使用给定[数据集](https://www.kaggle.com/crawford/80-cereals)的示例。

**例 1:**

在本程序中，我们将更改颜色或突出显示条形图中那些*等级*大于或等于 80 的*名称*。

## 蟒 3

```
# Import required module
import altair as alt
import pandas as pd

df = pd.read_csv("cereal.csv")
alt.Chart(df).mark_bar().encode(
    x='name',
    y="rating",

    # The highlight is set based on the result 
    # of the conditional statement
    color=alt.condition(
        alt.datum.rating >= 80,  # If the rating is 80 it returns True,
        alt.value('green'),      # and the matching bars are set as green.
        # and if it does not satisfy the condition 
        # the color is set to steelblue.
        alt.value('steelblue')
    )
).properties(width=500)
```