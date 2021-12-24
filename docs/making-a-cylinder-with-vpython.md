# 用 VPython 制作圆柱体

> 原文:[https://www . geesforgeks . org/making-a-cylinder-with-vpython/](https://www.geeksforgeeks.org/making-a-cylinder-with-vpython/)

**`VPython`** 可以轻松创建可导航的 3D 显示和动画，即使对于编程经验有限的人来说也是如此。因为它基于 Python，所以它也可以为有经验的程序员和研究人员提供很多东西。`VPython`允许用户在三维空间中创建球体和圆锥体等对象，并在窗口中显示这些对象。这使得创建简单的可视化变得容易，允许程序员将更多的精力放在程序的计算方面。`VPython`的简单性使它成为简单物理的图解工具，尤其是在教育环境中。

**安装:**

```py
pip install vpython
```

**圆柱体**是三维空间中的几何对象，具有直的平行边和圆形或椭圆形横截面。我们可以使用`cylinder()`方法在`VPython`中生成一个圆锥体。

## 气缸()

> **语法:**圆柱体(参数)
> 
> **参数:**
> 
> *   **pos :** 是气缸一端中心的位置。指定包含 3 个值的向量，例如 pos = vector(0，0，0)
> *   **轴:**是圆柱体的对中轴。指定包含 3 个值的向量，例如轴=向量(1，2，1)
> *   **up :** 是气缸的方位。指定一个包含 3 个值的向量，例如 up = vector(0，1，0)
> *   **颜色:**是圆柱体的颜色。指定一个包含 3 个值的向量，例如 color = vector(1，1，1)将给出白色
> *   **不透明度:**是圆柱体的不透明度。分配一个浮动值，其中 1 是最不透明的，0 是最不透明的，例如不透明度= 0.5
> *   **光泽:**是圆柱体的光泽。指定一个浮动值，其中 1 是最闪亮的，0 是最不闪亮的，例如闪亮度= 0.6
> *   **发射率:**是圆柱体的发射率。指定一个布尔值，其中“真”是发射性的，“假”不是发射性的，例如发射率=假
> *   **纹理:**是圆柱体的纹理。从纹理类中指定所需的纹理，例如纹理=纹理.灰泥
> *   **长度:**是圆柱体的长度。分配一个浮点值，默认长度为 1，示例长度= 10
> *   **半径:**是圆柱体的半径。指定一个浮动值，默认高度为 1，例如半径= 5
> *   **尺寸:**是圆柱体的尺寸。指定一个包含 3 个值的向量，分别代表长度、高度和宽度，例如大小=向量(1，1，1)
> 
> 所有参数都是可选的。

**例 1 :** 一个没有参数的圆柱体，所有参数都会有默认值。

```py
# import the module
from vpython import * cylinder()
```

**输出:**
![](img/eeddd58e7436235ff87348c1844f906a.png)

**示例 2 :** 使用颜色、不透明度、光泽和发射率参数的圆柱体。

```py
# import the module
from vpython import * cone(color = vector(0, 1, 1), 
     opacity = 0.5, 
     shininess = 1, 
     emissive = False)
```

**输出:**
![](img/8d72abb2bcaca4853b03e1e498f7862b.png)

**示例 3 :** 显示 2 个圆柱体，以可视化位置、长度和半径属性。

```py
# import the module
from vpython import *

# the first cylinder
cylinder(pos = vector(-2, 2, 0),
          length = 3,
          radius = 1,
          color = vector(0.5, 0, 0))

# the second cylinder
cylinder(pos = vector(1, -1, 5), 
          color = vector(0, 1, 0))
```

**输出:**
![](img/c98336f39447f3838797538797d570f8.png)

**示例 4 :** 使用纹理、轴和向上参数的圆柱体。

```py
# import the module
from vpython import * cylinder(texture = textures.stucco,
         axis = vector(-1, 4, 0),
         up = vector(1, 2, 2))
```

**输出:**
![](img/7ac2ffe71edbe3895afd097601613670.png)