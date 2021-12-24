# PIL 图像增强

> 原文:[https://www.geeksforgeeks.org/image-enhancement-in-pil/](https://www.geeksforgeeks.org/image-enhancement-in-pil/)

**Python 图像库(PIL)** 增加了强大的图像处理功能。它提供了巨大的文件格式支持、高效的表示和相当强大的图像处理能力。核心图像库旨在快速访问以非常少的基本像素格式存储的数据。它为通用图像处理工具提供了坚实的基础。

### 使用 PIL 的步骤

**步骤 1:** 从 PIL 图书馆导入图像模块

```
from PIL import Image
```

该模块提供了一个具有相同名称的类，用于表示 PIL 图像。并且还提供各种功能，包括从文件加载图像和创建新图像的功能。我不会在这里解释整个图像模块。但是，以下是打开图像文件的方法。

```
image_variable_name = Image.open("lena.jpg")
```

我们将在这里使用一个 PNG 图像。**有一点要记住——你在这里使用的图像文件必须存在于你的程序所在的同一个目录中。否则在引号内使用图像文件的完整路径。**

现在，您可以在图像查看器中看到带有一行代码的图像。

```
image_variable_name.show()
```

**步骤 2:** 现在是时候从 PIL 图书馆导入最重要的模块——“图像增强”模块了

```
from PIL import ImageEnhance
```

图像增强模块包含将用于图像增强的各种类。

### 我们可以用于增强的类

所有增强类都实现了一个典型的接口，包含一个名为“增强(因子)”方法的方法。

> pil . image enhanced .[方法](image_variable_name)
> 
> 方法可以是亮度、颜色、对比度、锐度。
> 
> **参数:**enhance()方法只取一个参数因子，即一个浮点。
> **返回类型:**此方法返回增强图像。

课程如下:

#### **亮度():**

调整图像亮度。它习惯于控制最终图像的亮度。亮度代码如下:

**输入:**

![](img/7b7bd75f63720acb95fb357c87949991.png)

## 蟒蛇 3

```
from PIL import Image
from PIL import ImageEnhance

# Opens the image file
image = Image.open('gfg.png')  

# shows image in image viewer
image.show()  

# Enhance Brightness
curr_bri = ImageEnhance.Brightness(image)
new_bri = 2.5

# Brightness enhanced by a factor of 2.5
img_brightened = curr_bri.enhance(new_bri)

# shows updated image in image viewer
img_brightened.show()  
```

增强因子 0.0 产生全黑图像，增强因子 1.0 产生与原始图像相同的结果。

**输出:**

![](img/8663c38c3b1dd0f2d33b0626ff687944.png)

#### 颜色():

调整图像颜色级别。它习惯于控制最终图像的颜色级别。着色代码如下:

**输入:**

![](img/7b7bd75f63720acb95fb357c87949991.png)

## 蟒蛇 3

```
from PIL import Image
from PIL import ImageEnhance

# Opens the image file
image = Image.open('gfg.png')

# shows image in image viewer
image.show()

# Enhance Color Level
curr_col = ImageEnhance.Color(image)
new_col = 2.5

# Color level enhanced by a factor of 2.5
img_colored = curr_col.enhance(new_col)

# shows updated image in image viewer
img_colored.show()
```

增强因子为 0.0 会产生完整的黑白图像，增强因子为 1.0 会产生与原始图像相同的结果。

**输出:**

![](img/fa7e6940659e9ce8c1d346b5b31eb5c5.png)

#### 对比度():

调整图像对比度。它习惯于控制最终图像的对比度。改变对比度的代码如下:

**输入:**

![](img/7b7bd75f63720acb95fb357c87949991.png)

## 蟒蛇 3

```
from PIL import Image
from PIL import ImageEnhance

# Opens the image file
image = Image.open('gfg.png')

# shows image in image viewer
image.show()

# Enhance Contrast
curr_con = ImageEnhance.Contrast(image)
new_con = 0.3

# Contrast enhanced by a factor of 0.3
img_contrasted = curr_con.enhance(new_con)

# shows updated image in image viewer
img_contrasted.show()  
```

增强因子 0.0 产生全灰度图像，增强因子 1.0 产生与原始图像相同的结果。

**输出:**

![](img/c4923eb0b7bc1d42e233d6ae972337b9.png)

#### 锐度():

调整图像清晰度。它习惯于控制最终图像的清晰度。改变清晰度的代码如下:

**输入:**

![](img/7b7bd75f63720acb95fb357c87949991.png)

## 蟒蛇 3

```
from PIL import Image
from PIL import ImageEnhance

# Opens the image file
image = Image.open('gfg.png')

# shows image in image viewer
image.show()

# Enhance Sharpness
curr_sharp = ImageEnhance.Contrast(image)
new_sharp = 8.3

# Sharpness enhanced by a factor of 8.3
img_sharped = curr_sharp.enhance(new_sharp)

# shows updated image in image viewer
img_sharped.show()
```

增强因子 0.0 导致图像模糊，增强因子 1.0 导致与原始图像相同，因子> 1.0 导致图像锐化。

**输出:**

![](img/5134cd0cf1268c24966edeb7a793e4a4.png)

这 4 类是最常用的，用来增强一个形象。那里还有很多其他功能。不要在这里停止学习，多去自己探索。