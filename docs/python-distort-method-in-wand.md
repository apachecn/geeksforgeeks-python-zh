# Python–魔杖中的扭曲()方法

> 原文:[https://www . geeksforgeeks . org/python-扭曲魔杖方法/](https://www.geeksforgeeks.org/python-distort-method-in-wand/)

ImageMagick 通过对用户提供的参数应用各种转换，提供了几种扭曲图像的方法。在魔杖中，使用了**扭曲()**的方法，并遵循一个基本函数。

**语法:**

```py
wand.image.distort(method, arguments, best_fit)
```

**参数:**

<figure class="table">

| 参数 | 输入类型 | 描述 |
| --- | --- | --- |
| 方法 | 基绳 | 黑点，占系统量子范围的百分比。默认为 0.. |
| 争论 | 集合. abc .序列 | 失真 _ 方法中的失真方法名称。 |
| 最适合 | 弯曲件 | 尝试调整结果图像的大小以适应失真。默认值为假。
 |

</figure>

以下是变形方法:

<figure class="table">

| 失真方法 | 描述 |
| --- | --- |
| '未定义' | 默认失真方法 |
| 仿射 | 平行型失真。 |
| “仿射投影” | 一种 3 平行四边形投影。 |
| “缩放 _ 旋转 _ 平移” | 转换失真 |
| “透视” | 三维向外投影失真。 |
| 透视投影 | 创造一个遥远的视角。 |
| “双线性向前” | 基于双线性方程。 |
| “双线性 _ 反向” | 基于反向双线性方程。 |
| 多项式 | 基于多项式。 |
| '弧' | 创建图像的圆形曲线。 |
| 极地 | 创建极轴扭曲效果。 |
| 去极化 | 产生去极化失真效果。 |
| '圆柱体 _ 2 _ 平面' | 创建圆柱体到平面的变形效果。 |
| ' plane _ 2 _ 柱面' | 创建平面到圆柱体的变形效果。 |
| 桶 | 在二维图像上创建向外凸起。 |
| 桶 _ 反向' | 在二维图像上创建向内凸起。 |
| “调整大小” | 调整失真图像的大小。 |
| 哨兵报 | 造成哨兵图像失真。 |

</figure>

**来源图片:**

![](img/3b4ee0698acd658ee9bd4a16ab6c636a.png)

**代码示例 1:**

## 蟒蛇 3

```py
# Import Image from wand.image module
from wand.image import Image

# Read image using Image function
with Image(filename ="gog.png") as img:
    img.distort('arc', (45, ))
    img.save(filename ='gogdistort1.png')
```

**输出图像:**

![](img/99621edb52da44e87edd091d7507cf74.png)

**代码示例 2:**
将扭曲 _ 方法更改为“透视”。

## 蟒蛇 3

```py
# Import Image from wand.image module
from wand.image import Image

# Read image using Image function
with Image(filename ="gog.png") as img:
    arguments = (0, 0, 20, 60,
                 90, 0, 70, 63,
                 0, 90, 5, 83,
                 90, 90, 85, 88)
    img.distort('perspective', arguments)
    img.save(filename ='gogdistort.png')
```

**输出图像:**

![](img/9b72fcf6132d0688de48a195e578b1cd.png)