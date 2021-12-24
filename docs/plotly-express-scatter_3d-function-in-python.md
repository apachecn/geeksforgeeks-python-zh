# Python 中的 plot . express .散点 _3d()函数

> 原文:[https://www . geeksforgeeks . org/plotly-express-散点 _ 3d-python 中的函数/](https://www.geeksforgeeks.org/plotly-express-scatter_3d-function-in-python/)

Python 的 Plotly 库对于数据可视化和简单容易地理解数据非常有用。Plotly graph 对象是易于使用的高级绘图界面。

## plotly.express.scatter_3d()函数

该功能用于创建三维散点图，并可用于熊猫数据帧。在散点图中，数据帧的每一行都由三维空间中的符号标记表示。

> **语法:**plot . express . scatter _ 3d(data _ frame =None，x=None，y=None，z=None，color=None，symbol=None，size=None，text=None，hover_name=None，hover_data=None，custom_data=None，error_x=None，error _ x _ 减=None，error_y=None，error_y 减=None，error_z=None，error _ z _ 减= None，animation_frame=None，animation_group=None，category_orders
> 
> **参数:**
> 
> **data_frame:** 列名需要传递 DataFrame 或类似数组或 dict。
> 
> **x，y，z:** 这些参数要么是 data_frame 中某列的名称，要么是 pandas Series 或 array_like 对象。来自该列或 array_like 的值分别用于在笛卡尔坐标中沿 x、y 和 z 轴定位标记。
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

**例 1:**

## 蟒蛇 3

```py
# Python program to demonstrate 3D scatter
# plot

import plotly.express as px

df = px.data.tips()

plot = px.scatter_3d(df, x = 'day', 
                     y = 'total_bill',
                     z='sex')
plot.show()
```

**输出:**

![](img/355e6e2eac9839faec7b657f06a3e79c.png)

**示例 2:** 使用颜色参数

## 蟒蛇 3

```py
# Python program to demonstrate scatter
# plot

import plotly.express as px

df = px.data.tips()

plot = px.scatter_3d(df, x = 'day', 
                     y = 'total_bill',
                     z = 'sex', 
                     color = 'time')
plot.show()
```

**输出:**

![](img/2864390e6dd6b0425fd4d1555fb803ef.png)

**例 3:**

## 蟒蛇 3

```py
# Python program to demonstrate scatter
# plot

import plotly.express as px

df = px.data.tips()

plot = px.scatter_3d(df, x = 'day', 
                     y = 'total_bill', 
                     z = 'sex', 
                     color = 'time',
                     symbol = 'total_bill')
plot.show()
```

**输出:**

![](img/a4e409533e51c37e27f06684048e859e.png)