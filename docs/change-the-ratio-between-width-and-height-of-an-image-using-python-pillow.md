# 使用 Python–枕头

更改图像的宽高比

> 原文:[https://www . geeksforgeeks . org/change-使用 python 更改图像的宽高比-/](https://www.geeksforgeeks.org/change-the-ratio-between-width-and-height-of-an-image-using-python-pillow/)

[**Python 图像库(PIL 的扩展)**](https://www.geeksforgeeks.org/python-pillow-a-fork-of-pil/#:~:text=Python%20Imaging%20Library%20(expansion%20of,editing%2C%20creating%20and%20saving%20images.) 是 Python 语言事实上的图像处理包。它集成了轻量级图像处理工具，有助于编辑、创建和保存图像。本模块未预装 Python。要安装它，请在命令行中执行以下命令:

```
pip install pillow
```

为了改变高度和宽度的比例，我们将从它们中添加或减去任何随机值。

### 使用的功能

*   **Image.open(fp，mode='r ')方法:**此方法用于打开图像。
*   **Image.resize(大小，重采样=0)方法:**此方法用于调整图像大小。在调整大小的过程中会发生插值，因此无论是放大(调整到比原始图像更高的尺寸)还是缩小(调整到比原始图像更低的图像)，图像的质量都会发生变化。

### **进场:**

*   我们先拍一张照片。
*   然后我们会发现它的高度和宽度。
*   然后我们将从它们中加减任何随机数来改变比率。
*   然后我们将保存图像。

**示例:**

**使用的图像:**

![](img/4dbb0f54608329250455b44fecfb5652.png)

## 蟒蛇 3

```
# Python program to change the ratio of height and
# width of an image 
from PIL import Image

# Taking image as input
img = Image.open('logo.png')

# Getting height and width of the image
height = img.size[0]
width = img.size[1]

# Printing ratio before conversion
print('Ratio before conversion:', width/height)

# Changing the height and width of the image
width = width + 25
height = height - 25

# Resizing the image
img = img.resize((width ,height), Image.ANTIALIAS)

# Printing the ratio after conversion
print('Ratio after conversion:', width/height)

# Saving the resized image
img.save('Resized Image.png')
```

**输出:**

```
Ratio before conversion: 1.0
Ratio after conversion: 1.25
```

**输出图像:**

![](img/f1cdf813fc771ad34b59a6ede5c06bf6.png)