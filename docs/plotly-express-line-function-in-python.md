# Python 中的 plot . express . line()函数

> 原文:[https://www . geesforgeks . org/plotly-express-line-function-in-python/](https://www.geeksforgeeks.org/plotly-express-line-function-in-python/)

Python 的 Plotly 库对于数据可视化和简单容易地理解数据非常有用。Plotly graph 对象是易于使用的高级绘图界面。

## plotly.express.line()函数

该功能用于创建线图。它也可以使用 pandas dataframe 创建，其中 data_frame 的每一行都表示为 2D 空间中折线标记的顶点。

> **语法:**plot . express . line(data _ frame =无，x =无，y =无，line _ group =无，color =无，line _ dash =无，hover _ name =无，hover _ data =无，title =无，模板=无，宽度=无，高度=无)
> 
> **参数:**
> 
> **data_frame:** 列名需要传递 DataFrame 或类似数组或 dict。
> 
> **x，y:** 该参数或者是 data_frame 中某列的名称，或者是 pandas Series 或 array_like 对象。来自该列或 array_like 的值分别用于在笛卡尔坐标中沿 x 轴和 y 轴定位标记。
> 
> **颜色:**该参数为标记指定颜色。
> 
> **line_group:** 此参数用于将 data_frame 的行分组为行。
> 
> **线划线:**该参数用于为线指定划线图案。
> 
> **悬停 _ 名称:**此列或类似数组的值以粗体显示在悬停工具提示中。
> 
> **悬停 _ 数据:**此参数用于在悬停工具提示或元组中以 bool 或格式字符串作为第一个元素出现，列表状数据作为第二个元素出现在悬停中这些列的值作为额外数据出现在悬停工具提示中。

**例 1:**

## 蟒蛇 3

```
import plotly.express as px

df = px.data.tips()

plot = px.line(df, x = 'day', y = 'time')
plot.show()
```

**输出:**

![](img/2c7f90bce1a1b060cbb3fc966fc8daf9.png)

**示例 2:** 使用颜色参数

## 蟒蛇 3

```
import plotly.express as px

df = px.data.tips()

plot = px.line(df, x = 'time', 
               y = 'total_bill',
               color = 'sex')
plot.show()
```

**输出:**

![](img/91d55ccf10c1b7d722ad6ecd646a7760.png)

**示例 3:** 使用 line_group 参数

## 蟒蛇 3

```
import plotly.express as px

df = px.data.tips()

plot = px.line(df, x = 'time',
               y = 'total_bill',
               color = 'sex', 
               line_group = 'day')

plot.show()
```

**输出:**

![](img/850a72468aafd5df48dec6a70a524ef5.png)