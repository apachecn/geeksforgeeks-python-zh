# 使用 Python 以循环方式裁剪图像

> 原文:[https://www . geeksforgeeks . org/使用 python 以循环方式裁剪图像/](https://www.geeksforgeeks.org/cropping-an-image-in-a-circular-way-using-python/)

在本文中，我们将学习使用枕头库循环裁剪图像。循环裁剪图像意味着选择图像内部的圆形区域，并移除圆形以外的所有内容。

**进场:**

*   如果您有一个 L 模式的图像，图像会变成灰度。所以我们用“L”模式创建了一个新的图像。
*   创建的图像中间有一个白色圆圈，其尺寸与输入图像相同。
*   将新图像转换为数组。
*   从数组转换原始图像。
*   将这两个数组堆叠在一起，只裁剪出圆形的中间部分。

**我们来看这张初始图像:**

![](img/02eace76ef1bf4ee3d8b32e3fb974601.png)

**第一步:**导入模块，读取图像。

## 蟒蛇 3

```py
import numpy as np
from PIL import Image, ImageDraw

img = Image.open("/content/gfg.jpeg")
display(img)
```

**输出:**

![](img/02eace76ef1bf4ee3d8b32e3fb974601.png)

**步骤 2:** 创建图像。

我们将使用 pieslice()函数获得白色图像的圆形部分，然后我们将叠加原始图像和发光图像。

**ImageDraw。Draw.pieslice()** 与弧相同，但也在端点和边界框中心之间绘制直线。

> ***句法:** PIL。ImageDraw.Draw.pieslice(xy，开始，结束，填充=无，轮廓=无)*
> 
> ***参数:***
> ***xy**–定义包围盒的四个点。[(x0，y0)，(x1，y1)]或[x0，y0，x1，y1]的序列。*
> ***开始**–开始角度，单位为度。角度从 3 点开始测量，顺时针方向增加。*
> ***终点**–终点角度，单位为度。*
> ***填充**–用于填充的颜色。*
> ***轮廓**–用于轮廓的颜色。*
> 
> ***返回:**切片形状的图像对象。*

**代码:**

## 蟒蛇 3

```py
h,w = img.size

# creating luminous image
lum_img = Image.new('L',[h,w] ,0) 
draw = ImageDraw.Draw(lum_img)
draw.pieslice([(0,0),(h,w)],0,360,fill=255)
img_arr = np.array(img)
lum_img_arr = np.array(lum_img)
display(Image.fromarray(lum_img_arr))
```

**输出:**

![](img/a16419083761eb248c232c74e83858ea.png)

**第三步:**将这两个数组叠加在一起，只裁剪出圆形的中间部分。

## 蟒蛇 3

```py
final_img_arr = np.dstack((img_arr, lum_img_arr))
display(Image.fromarray(final_img_arr))
```

**输出:**

![](img/bed80866f5975d14d85fcc9a153989aa.png)

**以下是完整实现:**

## 蟒蛇 3

```py
import numpy as np
from PIL import Image, ImageDraw

img=Image.open("img.jpg")
display(img)

height,width = img.size
lum_img = Image.new('L', [height,width] , 0)

draw = ImageDraw.Draw(lum_img)
draw.pieslice([(0,0), (height,width)], 0, 360, 
              fill = 255, outline = "white")
img_arr =np.array(img)
lum_img_arr =np.array(lum_img)
display(Image.fromarray(lum_img_arr))
final_img_arr = np.dstack((img_arr,lum_img_arr))
display(Image.fromarray(final_img_arr))
```

**输出:**

![](img/bed80866f5975d14d85fcc9a153989aa.png)