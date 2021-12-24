# Python–魔杖中的 color_matrix()函数

> 原文:[https://www . geesforgeks . org/python-color _ matrix-in-function-in-wand/](https://www.geeksforgeeks.org/python-color_matrix-function-in-wand/)

**color_matrix()** 方法允许您通过应用矩阵变换来重新计算颜色值。一个矩阵可以是一个 6×6 的网格，其中每一列映射到一个要引用的颜色通道，每一行代表一个要生效的颜色通道，红、绿、蓝、n/a、alpha 和一个常数(也称为偏移量)描述了相应的行和列。
T3】

> **语法:**
> 
> ```py
> wand.image.color_matrix(matrix)
> 
> ```
> 
> **参数:**
> 
> | 参数 | 输入类型 | 描述 |
> | --- | --- | --- |
> | 矩阵 | 集合. abc .序列 | 双打 2d 名单。 |

**来源影像:**
![](img/a1d5dabac07efe8de363e0c440a198d8.png)

**例 1:**

```py
# Import Image from wand.image module
from wand.image import Image

# Read image using Image function
with Image(filename ="koala.jpeg") as img:
    matrix = [[0, 0, 1],
              [0, 1, 0],
              [1, 0, 0]]
    # Recalculate color using color_matrix() method
    img.color_matrix(matrix)
    img.save(filename ="cm_koala.jpeg")
```

**输出:**
![](img/a5317b5095c4762f8160e0892f40cd18.png)

**例 2:**

```py
# Import Image from wand.image module
from wand.image import Image

# Read image using Image function
with Image(filename ="koala.jpeg") as img:
    matrix = [[0, 1, 0],
              [1, 0, 0],
              [0, 0, 1]]
    # Recalculate color using color_matrix() method
    img.color_matrix(matrix)
    img.save(filename ="cm_koala2.jpeg")
```

**输出:**
![](img/31a75b0519927b2accea5b90a2171bbc.png)