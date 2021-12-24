# Python 中的 3D 热图

> 哎哎哎:# t0]https://www . geeksforgeeks . org/3d-heat map-in-python/

**热图**是可视化数据集的好方法，可视化数据的方法不断被探索，3D 热图是绘制数据的方法之一。让我们学习如何用 python 绘制 3D 数据。我们将使用 matplotlib 和 mplot3d 在 Python 中绘制 3d 热图。我们需要通过在控制台中运行以下命令来显式安装 matplotlib】

## **创建 3D 热图**

*   在这个代码示例中，首先我们使用语句 **%matplotlib** 在 jupyter 笔记本内内联显示所有 matplotlib 图。然后，我们导入了运行此代码示例所需的所有必要库–mplot 3d 库用于绘制 3d 图，pyplot 主要用于绘制图形及其配置。
*   之后，我们使用 NumPy randint 函数为 3d 热图创建了一个随机数据集，以创建一个随机整数数组。
*   使用**PLT . fig**，我们已经创建了一个尺寸分别为 10×10 的宽度和高度的图形，默认情况下 matplotlib 将生成 2D 图，因此要将其指定为 3d 图，我们使用 **add_subplot** 函数，并使用**投影='3d'** 来创建 3d 图。
*   我们使用 **set_array()** 函数将整数数组映射为 RGBA 颜色。
*   之后，我们用我们的 3d 数据集创建散点图，通过将**标记值**设置为**，我们将每个数据点显示为方形。它们的颜色将取决于我们之前创建的名为 **colo.** 的阵列**
*   **最后，我们使用 set_label 功能设置了 x、y、z 标签和标题，并使用 **show** ()功能显示了图形。**

****代号:****

 **## 蟒 3

```py
# 3D Heatmap in Python using matplotlib

# to make plot interactive 
%matplotlib

# importing required libraries
from mpl_toolkits.mplot3d import Axes3D
import matplotlib.pyplot as plt
import numpy as np
from pylab import *

# creating a dummy dataset
x = np.random.randint(low=100, high=500, size=(1000,))
y = np.random.randint(low=300, high=500, size=(1000,))
z = np.random.randint(low=200, high=500, size=(1000,))
colo = [x + y + z]

# creating figures
fig = plt.figure(figsize=(10, 10))
ax = fig.add_subplot(111, projection='3d')

# setting color bar
color_map = cm.ScalarMappable(cmap=cm.Greens_r)
color_map.set_array(colo)

# creating the heatmap
img = ax.scatter(x, y, z, marker='s',
                 s=200, color='green')
plt.colorbar(color_map)

# adding title and labels
ax.set_title("3D Heatmap")
ax.set_xlabel('X-axis')
ax.set_ylabel('Y-axis')
ax.set_zlabel('Z-axis')

# displaying plot
plt.show()
```**