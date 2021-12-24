# 用 Python 创建并保存动画 GIF–枕头

> 原文:[https://www . geesforgeks . org/create-and-save-animated-gif-with-python-pizzle/](https://www.geeksforgeeks.org/create-and-save-animated-gif-with-python-pillow/)

**先决条件:** [枕](https://www.geeksforgeeks.org/python-pillow-a-fork-of-pil/)

在本文中，我们将使用枕头库来创建和保存 gif。

**GIFs:** 图形交换格式(gif)是一种位图图像格式，由美国计算机科学家史蒂夫·威尔海特领导的在线服务提供商 CompuServe 的一个团队于 1987 年 6 月 15 日开发的。

一个 GIF 文件通常存储一个图像，但该格式允许多个图像存储在一个文件中。该格式还具有参数，可用于对图像进行排序，以在短时间内显示每个图像，然后用下一个图像替换它。简单来说，GIF 就是一个运动图像。

**枕头:**枕头用于 python 中的图像处理。枕头是在 PIL(python 图像库)的基础上开发的。python 3 不支持 PIL，所以我们使用枕头。

本模块未预装 Python。要安装它，请在命令行中执行以下命令:

```py
pip install pillow
```

**让我们逐步创建一个****gif:**

**步骤 1:** 首先我们导入我们对 PIL 模块的需求。

## 蟒 3

```py
from PIL import Image, ImageDraw
```

**第二步:**在我们输入圆的值后，创建一个列表。(0，255，0)是绿色的色码，(255，0，0)是红色的色码。

## 蟒 3

```py
images = []
width = 200
center = width // 2
color_1 = (0,255, 0)
color_2 = (255, 0, 0)
max_radius = int(center * 1.5)
step = 8
```