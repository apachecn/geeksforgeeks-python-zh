# Python 中的 plot . express . scatter _ polar()函数

> 原文:[https://www . geesforgeks . org/plotly-express-spread _ polar-function-in-python/](https://www.geeksforgeeks.org/plotly-express-scatter_polar-function-in-python/)

Python 的 Plotly 库对于数据可视化和简单容易地理解数据非常有用。Plotly graph 对象是易于使用的高级绘图界面。

## plotly.express.scatter_polar()函数

该功能用于创建极坐标图。极坐标图表示沿径向和角度轴的数据。

> **语法:**plot . express . scatter _ polar(data _ frame = None，r=None，theta=None，color=None，symbol=None，size=None，hover_name=None，hover_data=None，title=None，template=None，width=None，height=None)
> 
> **参数:**
> 
> **data_frame:** 列名需要传递 DataFrame 或类似数组或 dict。
> 
> **r，theta:** 该参数或者是 data_frame 中某列的名称，或者是 pandas Series 或 array_like 对象。用于在极坐标中分别沿径向轴和角向轴定位标记。
> 
> **颜色:**该参数为标记指定颜色。
> 
> **符号:**此参数用于将符号分配给标记。它或者是 data_frame 中某列的名称，或者是 pandas Series 或 array_like 对象。
> 
> **尺寸:**该参数用于分配标记尺寸。它或者是 data_frame 中某列的名称，或者是 pandas Series 或 array_like 对象。
> 
> **悬停 _ 名称:**此列或类似数组的值以粗体显示在悬停工具提示中。
> 
> **悬停 _ 数据:**此参数用于在悬停工具提示或元组中以 bool 或格式字符串作为第一个元素出现，列表状数据作为第二个元素出现在悬停中这些列的值作为额外数据出现在悬停工具提示中。
> 
> **标题:**图标题
> 
> **宽度:**以像素为单位的图形宽度。
> 
> **高度:**以像素为单位的图形高度。

**例 1:**

## 蟒蛇 3

```
import plotly.express as px

df = px.data.tips()

plot = px.scatter_polar(df, r = 'day', 
                        theta = 'total_bill')
plot.show()
```

**输出:**

![](img/d65ec4b51c4eaad1c626c84dd643cb76.png)

**示例 2:** 使用颜色参数

## 蟒蛇 3

```
import plotly.express as px

df = px.data.tips()

plot = px.scatter_polar(df, r = 'day',
                        theta = 'total_bill', 
                        color='time')
plot.show()
```

**输出:**

![](img/5426f5e899b1392e2791c08e46af3421.png)

**示例 3:** 使用符号参数

## 蟒蛇 3

```
import plotly.express as px

df = px.data.tips()

plot = px.scatter_polar(df, r = 'day', 
                        theta = 'total_bill',
                        color = 'time',
                        symbol = 'tip')
plot.show()
```

**输出:**

![](img/6095eb9e8f12172b95505ab59ba9b4b4.png)