# Python | PIL 属性

> 原文:[https://www.geeksforgeeks.org/pyhton-pil-attributes/](https://www.geeksforgeeks.org/pyhton-pil-attributes/)

PIL is the Python Imaging Library which provides the python interpreter with image editing capabilities.

## 属性:

属性定义了对象、元素或文件的各种属性。在图像中，属性指的是大小、文件名、格式或模式等。图像的。

所用图像为:
![](img/3f2afcf79d83eee360e00663a300d18c.png)

图像类的实例具有以下属性:

**PIL。Image.filename:** 源文件的文件名或路径。只有在工厂功能打开的情况下创建的图像才有文件名属性。如果输入是类似文件的对象，filename 属性将设置为空字符串。

```
Syntax: PIL.Image.filename

Type: py:class: string

```

```
from PIL import Image
im1 = Image.open(r"C:\Users\sadow984\Desktop\i3.PNG")

im2 = im1.filename
print(im2)
```

**输出:**

```
C:\Users\sadow984\Desktop\r1.PNG
```

**PIL。**源文件的文件格式。对于由库本身创建的图像(通过工厂函数，或通过在现有图像上运行方法)，此属性设置为无。

```
Syntax: PIL.Image.format

Type: string or None

```

```
from PIL import Image
im1 = Image.open(r"C:\Users\sadow984\Desktop\i3.PNG")

im2 = im1.format
print(im2)
```

**输出:**

```
PNG
```

**PIL。**图像模式。这是一个字符串，指定图像使用的像素格式。典型值为“1”、“L”、“RGB”或“CMYK”有关完整列表，请参见模式。

```
Syntax: PIL.Image.mode

Type: string 

```

```
from PIL import Image
im1 = Image.open(r"C:\Users\sadow984\Desktop\i3.PNG")

im2 = im1.mode
print(im2)
```

**输出:**

```
P
```

**PIL。**图像尺寸，以像素为单位。尺寸以二元组(宽度、高度)给出。

```
Syntax: PIL.Image.size

Type: (width, height) 

```

```
from PIL import Image
im1 = Image.open(r"C:\Users\sadow984\Desktop\i3.PNG")

im2 = im1.size
print(im2)
```

**输出:**

```
(225, 225)
```