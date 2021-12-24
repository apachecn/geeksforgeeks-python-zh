# 用 Python 给图像添加填充–枕头

> 原文:[https://www . geeksforgeeks . org/add-padding-to-to-image-with-pylori-枕/](https://www.geeksforgeeks.org/add-padding-to-the-image-with-python-pillow/)

**先决条件:**T2【枕(蟒库)

填充是内容、容器和边框之间的空间。图像可以被认为是某个容器的内容，可以在其中添加额外的填充。本文描述了如何做到这一点。填充可以通过直接为要填充的边提供值来添加。然后，这些值可以传递给函数来创建新的图像。

### 装置

本模块未预装 Python。要安装它，请在命令行中执行以下命令:

```
pip install pillow
```

### 方法

*   导入模块
*   打开图像
*   设置填充值
*   为图像设置不同的尺寸
*   将填充值传递给图像
*   保存新图像

**输入图像:**

![](img/c411ae9db78e0fc80a55e348ba3cfc58.png)

**程序:**

## 蟒蛇 3

```
from PIL import Image

image = Image.open("input.jpg")

right = 100
left = 100
top = 100
bottom = 100

width, height = image.size

new_width = width + right + left
new_height = height + top + bottom

result = Image.new(image.mode, (new_width, new_height), (0, 0, 255))

result.paste(image, (left, top))

result.save('output.jpg')
```

**输出:**

![](img/4618952525cc18dd196ac2b0b813c271.png)

生成的输出只是添加了填充的输入图像。在这里，它显示为一个边框，因为每一边给出的值是相等的。对于不同的值，可以观察到不均匀的填充。