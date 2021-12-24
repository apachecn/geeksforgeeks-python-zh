# Python 中的 plot . express .散点 _ 三元()函数

> 原文:[https://www . geeksforgeeks . org/plotly-express-散点 _ 三元-python 中的函数/](https://www.geeksforgeeks.org/plotly-express-scatter_ternary-function-in-python/)

Python 的 Plotly 库对于数据可视化和简单容易地理解数据非常有用。Plotly graph 对象是易于使用的高级绘图界面。

## plotly.express .散点 _ 三元()函数

此方法用于创建三元图。三元图用来描绘等边三角形上三个变量的比值。

> **语法:**plot . express .散点 _ 三元(data_frame=None，a=None，b=None，c=None，color=None，symbol=None，size=None，text=None，hover_name=None，hover_data=None，size_max=None，title=None，template=None，width=None，height=None)
> 
> **参数:**
> 
> **data_frame:** 列名需要传递 DataFrame 或类似数组或 dict。
> 
> **a、b、c:** 这些参数要么是 data_frame 中某列的名称，要么是 pandas Series 或 array_like 对象。这些分别用于在三元坐标中沿 a、b 和 c 轴定位标记。
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
> **标题:**图的标题。
> 
> **宽度:**设置图形的宽度。
> 
> **高度:**设置人物的高度。

**例 1:**

## 蟒蛇 3

```
import plotly.express as px

df = px.data.iris()

plot = px.scatter_ternary(df, a = 'sepal_width',
                          b = 'sepal_length', 
                          c = 'petal_width')
plot.show()
```

**输出:**

![](img/0efaef021a6b655c1f7c56855ddfa00e.png)

**示例 2:** 使用大小和颜色参数

## 蟒蛇 3

```
import plotly.express as px

df = px.data.iris()

plot = px.scatter_ternary(df, a = 'sepal_width', 
                          b = 'sepal_length',
                          c='petal_width',
                          color = 'species',
                          size = 'petal_length')
plot.show()
```

**输出:**

![](img/6aa126e02e22b60b84f09f970b32cfe5.png)

**示例 3:** 使用符号参数

## 蟒蛇 3

```
import plotly.express as px

df = px.data.iris()

plot = px.scatter_ternary(df, a = 'sepal_width',
                          b = 'sepal_length', 
                          c = 'petal_width', 
                          color = 'species',
                          size = 'petal_length',
                          symbol = 'species_id')
plot.show()
```

**输出:**

![](img/f0df9999617eb5eceaa30f69343cf3ff.png)