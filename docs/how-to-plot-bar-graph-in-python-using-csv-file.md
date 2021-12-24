# 如何用 CSV 文件在 Python 中绘制条形图？

> 原文:[https://www . geeksforgeeks . org/如何使用-csv-file 绘制 python 条形图/](https://www.geeksforgeeks.org/how-to-plot-bar-graph-in-python-using-csv-file/)

CSV 代表“逗号分隔值”，这意味着通过放入逗号和换行符来区分这些值。CSV 文件提供了一种类似表格的格式，几乎每个电子表格阅读器都可以阅读，如微软 Excel 和谷歌电子表格。

条形图使用标签和值，其中标签是特定条形图的名称，值表示条形图的高度。条形图通常用于数据分析，我们希望比较数据并提取最常见或最高的组。

在这篇文章中，我们将学习如何使用 CSV 文件绘制条形图。有很多模块可以用来读取. csv 文件，如 csv，熊猫等。但是在这篇文章中，我们将手动阅读。csv 文件来了解事情是如何运作的。

### 使用的功能

*   Pandas read_csv()函数用于读取 csv 文件。

**语法:**

> read_csv(“文件路径”)

*   Matplotlib's bar () function is used to create bar charts.

**语法:**

> 进度条(x，高，宽，底，对齐)

### 方法一:利用熊猫

**逼近**

*   Import module
*   Use the read_csv () function to read files.
*   Draw bar chart
*   Display graphics

**示例:**

**正在使用的数据集:** [单击此处](https://github.com/mukulbindal/Files/blob/main/data.csv)

## python 3

```py
# Import the necessary modules
import matplotlib.pyplot as plt
import pandas as pd

# Initialize the lists for X and Y
data = pd.read_csv('C:\\Users\\Vanshi\\Desktop\\data.csv')

df = pd.DataFrame(data)

X = list(df.iloc[:, 0])
Y = list(df.iloc[:, 1])

# Plot the data using bar() method
plt.bar(X, Y, color='g')
plt.title("Students over 11 Years")
plt.xlabel("Years")
plt.ylabel("Number of Students")

# Show the plot
plt.show()
```