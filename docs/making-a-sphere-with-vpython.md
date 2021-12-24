# 用 VPython 制作球体

> 原文:[https://www.geeksforgeeks.org/making-a-sphere-with-vpython/](https://www.geeksforgeeks.org/making-a-sphere-with-vpython/)

**`VPython`** 可以轻松创建可导航的 3D 显示和动画，即使对于编程经验有限的人来说也是如此。因为它基于 Python，所以它也可以为有经验的程序员和研究人员提供很多东西。`VPython`允许用户在三维空间中创建球体和圆锥体等对象，并在窗口中显示这些对象。这使得创建简单的可视化变得容易，允许程序员将更多的精力放在程序的计算方面。`VPython`的简单性使它成为简单物理的图解工具，尤其是在教育环境中。

**安装:**

```py
pip install vpython
```

一个**球体**是三维空间中的一个几何物体，是一个球的表面。我们可以使用`sphere()`方法在`VPython`中生成一个球体。

## 球体()

> **语法:**球体(参数)
> 
> **参数:**
> 
> *   **pos :** 是球体中心的位置。指定包含 3 个值的向量，例如 pos = vector(0，0，0)
> *   **轴:**是球体的对齐轴。指定包含 3 个值的向量，例如轴=向量(1，2，1)
> *   **up :** 是球体的方位。指定一个包含 3 个值的向量，例如 up = vector(0，1，0)
> *   **颜色:**是球体的颜色。指定一个包含 3 个值的向量，例如 color = vector(1，1，1)将给出白色
> *   **不透明度:**是球体的不透明度。分配一个浮动值，其中 1 是最不透明的，0 是最不透明的，例如不透明度= 0.5
> *   **光亮:**是球体的光亮。指定一个浮动值，其中 1 是最闪亮的，0 是最不闪亮的，例如闪亮度= 0.6
> *   **发射率:**是球体的发射率。指定一个布尔值，其中“真”是发射性的，“假”不是发射性的，例如发射率=假
> *   **纹理:**是球体的纹理。从纹理类中指定所需的纹理，例如纹理=纹理.灰泥
> *   **半径:**是球体的半径。指定一个浮动值，默认半径为 1，示例半径= 10
> *   **大小:**是球体的大小。分配一个包含 3 个值的向量，分别表示长度、高度和重量，默认大小为(2，2，2)，示例大小=向量(1，1，1)
> 
> 所有参数都是可选的。

**例 1 :** 一个没有参数的球体，所有参数都会有默认值。

```py
# import the module
from vpython import * sphere()
```

**输出:**
![](img/db123d20f1fe873f9ba05c09738091f1.png)

**示例 2 :** 使用颜色、不透明度、光泽和发射率参数的球体。

```py
# import the module
from vpython import * sphere(color = vector(5, 3, 1), 
       opacity = 0.5, 
       shininess = 1, 
       emissive = False)
```

**输出:**
![](img/b513cdfeef94f40292b53ade1d2dcc0d.png)

**示例 3 :** 显示 2 个球体以可视化属性位置和大小。

```py
# import the module
from vpython import *

# the first sphere
sphere(pos = vector(-1, 2, 0),
       size = vector(1, 1, 1),
       color = vector(15, 1, 1))

# the second sphere
sphere(pos = vector(1, -2, 0), 
       size = vector(3, 3, 3),
       color = vector(5, 10, 1))
```

**输出:**
![](img/336a56bac065d86c64296e31832763bc.png)

**示例 4 :** 使用纹理、轴和向上参数的球体。

```py
# import the module
from vpython import * sphere(texture = textures.stucco,
       axis = vector(1, 0, 0),
       up = vector(0, 1, 0))
```

**输出:**
<img src = " https://media . geeksforgeeks . org/WP-content/uploads/20200528102735/截图- ![](img/bee955f9c5998535af4f0830e004a80d.png)