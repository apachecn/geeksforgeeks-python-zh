# Python 中 ImageIO 库入门

> 原文:[https://www . geesforgeks . org/入门-imageio-python 库/](https://www.geeksforgeeks.org/getting-started-with-imageio-library-in-python/)

**Imageio** 是一个 Python 库，提供了一个简单的界面来读写各种各样的图像数据，包括动画图像、体积数据和科学格式。它是跨平台的。

### **安装:**

这个模块没有内置 Python。要安装它，请在终端中键入以下命令。

```py
pip install imageio
```

### 要求:

*   Python 3.5+
*   数字
*   枕头

进入输入图像文件[点击这里](https://drive.google.com/drive/folders/1-LiHXEXA7MAY16wGxfsquQHH5ZToJ3ic)。让我们看看 imageio 库的一些工作代码:

1) **读取图像:**为了读取图像，我们必须使用 **imageio.imread()** 方法。

> **语法:** imageio.imread(“文件名或路径”)
> 
> **参数:**
> 
> *   **文件名/路径:**图像文件的绝对或相对路径。
> 
> **Return:** 返回一个 numpy 数组，该数组在其“元”属性中带有一组元数据。

**示例:**

## 蟒蛇 3

```py
# import library
import imageio

# read an image
image = imageio.imread('testa.png')

# print shape of the image
print(image.shape) 
```

**输出:**

```py
(134, 151, 4)
```

2) **读取 GIF 文件:**为了读取一个 **GIF** 文件，我们不得不使用 **imageio.get_reader()** 方法。

> **语法:** imageio.get_reader(文件名、格式、模式)
> 
> **参数:**
> 
> *   **路径/文件名:**所需图像/文件/gif 的文件名。
> *   **格式:**字符串，用于读取文件的格式，默认情况下，imageio 根据文件名及其内容为您选择合适的格式。
> *   **模式:** {'i '，' I '，' V '，' V '，'？'}
>     *   用于向读者提示用户期望什么(默认为“？”)):
>     *   我想要一张照片
>     *   对于多个图像
>     *   “v”代表一卷
>     *   ' v '适用于多卷
>     *   ？因为不在乎
> 
> **返回:** Reader`object，可用于从指定文件中读取数据和元数据。

**示例:**

## 蟒蛇 3

```py
# import library
import imageio

# create an image object
image = imageio.get_reader('test.gif')

# iterating through matrix:
for i in image :

  # Each frame is a numpy matrix
  print(i.shape)
```

**输出:**

```py
(300, 354, 4)
(300, 354, 4)
(300, 354, 4)
(300, 354, 4)
(300, 354, 4)
(300, 354, 4)
(300, 354, 4)
(300, 354, 4)
(300, 354, 4)
(300, 354, 4)
(300, 354, 4)
(300, 354, 4)
(300, 354, 4)
(300, 354, 4)
(300, 354, 4)
(300, 354, 4)
```

3) **创建图像文件:**为了创建图像文件，我们必须使用 **imageio.imwrite()** 方法。

> **语法:**imageio . imrite(filename，numpy _ ndarray，format=None)
> 
> **参数:**
> 
> *   **文件名:**保存文件的路径/名称
> *   **numpy_ndarray:** 图像数据。必须是 NxM、NxMx3 或 NxMx4。
> *   **格式:**字符串，用于读取文件的格式。默认情况下，imageio 根据文件名及其内容选择适合您的。

**示例:**

## 蟒蛇 3

```py
# import required libraries
import imageio
import numpy as np

rows, cols = (5, 5) 

# create numpy 2-d array
arr = np.zeros((rows, cols))

# create an image
image = imageio.imwrite('image_writing.png', 
                     arr)
```

**输出:**

![](img/584c57a7d74357ec4d774b3a162070d4.png)

影像 _ 写入 png .. .png

由于数据值为零，因此这是一个 68 字节大小的空图像。