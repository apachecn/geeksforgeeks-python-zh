# 如何用 Python 生成条码？

> 原文:[https://www . geesforgeks . org/如何生成 python 中的条形码/](https://www.geeksforgeeks.org/how-to-generate-barcode-in-python/)

在本文中，我们将编写一个简短的脚本来使用 Python 生成条形码。我们将使用 **python-barcode** 模块，它是 **pyBarcode** 模块的分叉。该模块为我们提供了以 SVG 格式生成条形码的功能。 [**枕头**](https://www.geeksforgeeks.org/python-pillow-a-fork-of-pil/) 需要生成图像格式的条形码(如 png 或 jpg)。

### 需要的模块

*   **python-条形码:**该模块用于创建条形码作为 SVG 对象。它为我们提供了创建不同标准类型条形码的能力，如 EAN-8、EAN-13、EAN-14、UPC-A、JAN、ISBN-10、ISBN-13 等等。要安装此模块，请在终端中键入以下命令。

```py
pip install python-barcode 
```

*   [**枕头:**](https://www.geeksforgeeks.org/python-pillow-a-fork-of-pil/) 这是用来创建图像格式的条形码。要安装此模块，请在终端中键入以下命令。

```py
pip install pillow

```

在这里，我们将生成 EAN-13 格式的条形码。首先，让我们将其生成为一个 SVG 文件。

## 蟒 3

```py
# import EAN13 from barcode module
from barcode import EAN13

# Make sure to pass the number as string
number = '5901234123457'

# Now, let's create an object of EAN13
# class and pass the number
my_code = EAN13(number)

# Our barcode is ready. Let's save it.
my_code.save("new_code")
```