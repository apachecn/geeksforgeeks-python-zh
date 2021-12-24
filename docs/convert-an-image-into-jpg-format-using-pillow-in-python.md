# 使用 Python 中的枕头将图像转换为 jpg 格式

> 原文:[https://www . geesforgeks . org/convert-a-image-to-jpg-format-使用 python 中的枕头/](https://www.geeksforgeeks.org/convert-an-image-into-jpg-format-using-pillow-in-python/)

让我们看看如何在 Python 中将图像转换为 jpg 格式。与 jpg 格式相比，png 的大小更大。我们还知道，一些应用程序可能会要求较小尺寸的图像。因此，需要从 png(较大)转换为 jpg(较小)。
对于这个任务，我们将使用枕头模块的`[Image.convert()](https://www.geeksforgeeks.org/python-pil-image-convert-method/)`方法。

**算法:**

1.  从 PIL 导入映像模块，然后导入操作系统模块。
2.  使用`[Image.open()](https://www.geeksforgeeks.org/python-pil-image-open-method/)`方法导入要转换的图像。
3.  使用`[os.path.getsize()](https://www.geeksforgeeks.org/python-os-path-size-method/)`方法显示转换前图像的大小。
4.  使用`Image.convert()`方法转换图像。通过`"RGB"` 作为参数。
5.  使用`[Image.save()](https://www.geeksforgeeks.org/python-pil-image-save-method/)`方法导出图像。
6.  使用`os.path.getsize()`方法显示转换后图像的大小。

我们将转换以下图像:
![](img/438d0d25a9fe8b715f357e0aa22b8c04.png)

```py
# importing the module
from PIL import Image
import os

# importing the image 
im = Image.open("geeksforgeeks.png")
print("The size of the image before conversion : ", end = "")
print(os.path.getsize("geeksforgeeks.png"))

# converting to jpg
rgb_im = im.convert("RGB")

# exporting the image
rgb_im.save("geeksforgeeks_jpg.jpg")
print("The size of the image after conversion : ", end = "")
print(os.path.getsize("geeksforgeeks_jpg.jpg"))
```

**输出:**

```py
The size of the image before conversion : 26617
The size of the image after conversion : 18118

```