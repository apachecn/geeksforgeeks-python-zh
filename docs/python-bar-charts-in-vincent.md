# Python |文森特的条形图

> 原文:[https://www.geeksforgeeks.org/python-bar-charts-in-vincent/](https://www.geeksforgeeks.org/python-bar-charts-in-vincent/)

在本文中，我们将在文森特的帮助下创建条形图。python 中哪个库做 python 到 vega 的翻译？它具有 python 的数据能力和 javascript 的可视化能力。它是专门为快速绘制数据帧和系列而构建的。

**要求:安装文森特**

```py
$pip install vincent
```

**警告:**需要熊猫，熊猫需要数字

**示例 1:** 简单条形图

```py
# import the vincent library
import vincent

# To initialize vincent in the notebook
vincent.core.initialize_notebook()

# pass the parameters to the bar method
bar = vincent.Bar([30, 10, 20, 15, 45, 30, 5])

# Display the bar chart
bar.display()
```

**输出:**
![](img/a28fc6f637ae3bd566d7a53d814846c7.png)

**示例 2:** 带轴标签的条形图

```py
# import the vincent library
import vincent

# To initialize vincent in the notebook
vincent.core.initialize_notebook()

# pass the parameters to the bar method
bar = vincent.Bar([30, 10, 20, 15, 45, 30, 5])
# give axis names

bar.axis_titles(x ='X-axis', y ='Y-axis')

# Display the bar chart
bar.display()
```

**输出:**
![](img/f486b7ce8ffbff74d6cff4d42bc89398.png)

有关文森特条形图和文森特的更多信息，请访问此[链接](https://vincent.readthedocs.io/en/latest/quickstart.html#quick-data)