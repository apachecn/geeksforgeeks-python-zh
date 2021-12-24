# Python 中 plot . express . line _ 三元()函数

> 原文:[https://www . geesforgeks . org/plotly-express-line _ 三元-python 中的函数/](https://www.geeksforgeeks.org/plotly-express-line_ternary-function-in-python/)

Python 的 Plotly 库对于数据可视化和简单容易地理解数据非常有用。Plotly graph 对象是易于使用的高级绘图界面。

## plotly . express . line _ 三元()

该方法用于创建三元线图。三元线图用于描绘等边三角形上三个变量的比值。

> **语法:**plot . express . line _ 三元(data _ frame =无，a =无，b =无，c =无，color =无，line _ dash =无，line _ group =无，hover _ name =无，hover _ data =无，title =无，模板=无，宽度=无，高度=无)
> 
> **参数:**
> 
> **data_frame:** 列名需要传递 DataFrame 或类似数组或 dict。
> 
> **a、b、c:** 这些参数要么是 data_frame 中某列的名称，要么是 pandas Series 或 array_like 对象。这些分别用于在三元坐标中沿 a、b 和 c 轴定位标记。
> 
> **颜色:**该参数为标记指定颜色。
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

plot = px.line_ternary(df, a = 'sepal_width',
                          b = 'sepal_length', 
                          c = 'petal_width')
plot.show()
```

**输出:**

![](img/5aa7e6e611838c08c0c849311202db31.png)

**示例 2:** 使用颜色和线组参数

## 蟒蛇 3

```
import plotly.express as px

df = px.data.iris()

plot = px.line_ternary(df, a = 'sepal_width',
                          b = 'sepal_length', 
                          c = 'petal_width', 
                          color = 'species',
                          line_group = 'species')
plot.show()
```

**输出:**

![](img/90cdec86e04d629bacaa53952b74e021.png)