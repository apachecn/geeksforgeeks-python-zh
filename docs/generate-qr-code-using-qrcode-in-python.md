# 使用 Python 中的二维码生成二维码

> 原文:[https://www . geesforgeks . org/generate-QR-code-using-QR code-in-python/](https://www.geeksforgeeks.org/generate-qr-code-using-qrcode-in-python/)

一个 [**快速响应码**](https://en.wikipedia.org/wiki/QR_code) 或一个**二维码**是一个二维码，用于快速可读性和较大的存储容量。它由排列在白色背景上的正方形网格中的黑色正方形组成。

Python 有一个库“ [**【二维码】**](https://pypi.org/project/qrcode/) ”用于生成二维码图像。可以用 pip 安装。

```
pip install qrcode
```

**进场:**

*   导入模块
*   用 **qrcode.make()** 创建 Qrcode，它返回一个 PilImage 对象。
*   保存到图像中

**语法:**

```
qrcode.make('Data to be encoded')
```

**例 1:**

## 蟒蛇 3

```
# Importing library
import qrcode

# Data to be encoded
data = 'QR Code using make() fuction'

# Encoding data using make() function
img = qrcode.make(data)

# Saving as an image file
img.save('MyQRCode1.png')
```

**输出:**

![](img/daf4a28aa7702e22a82f86672b99e72c.png)

**例 2:**

我们也可以使用**二维码**类来创建一个二维码并更改其详细信息。它采用以下参数:

*   **版本:**该参数为 1-40 的整数，控制二维码的大小(最小的版本 1 是 21×21 矩阵)。
*   **纠错:**该参数控制二维码使用的纠错。有以下四个常量可供使用:
    *   ***二维码.常量. ERROR _ RESERVE _ L*****:**大约 7%或更少的错误可以被纠正。
    *   ***QR code . constants . error _ CORRECT _ M***(默认) **:** 大约 15%或更少的错误可以被纠正。
    *   ***二维码.常量. error _ CORRECT _ Q*****:**大约 25%或更少的错误可以被纠正。
    *   ***二维码.常量. ERROR _ RESERVE _ H*****:**大约 30%或更少的错误可以被纠正。
*   **box_size:** 该参数控制二维码每个“框”有多少像素。
*   **边框:**边框参数控制边框应该有多厚(默认值为 4，这是规格中的最小值)。
*   **add_data():** 这个方法是用来给二维码对象添加数据。它将待编码的数据作为参数。
*   **make():** 这种带有 **(fit=True)** 的方法可以确保二维码的整个维度得到利用，即使我们的输入数据可以放入更少的盒子中。
*   **make_image():** 此方法用于将二维码对象转换为图像文件。它采用 ***填充 _ 颜色*** 和 ***背景 _ 颜色*** 可选参数来设置前景和背景颜色。

**下面是实现:**

## 蟒蛇 3

```
# Importing library
import qrcode

# Data to encode
data = "GeeksforGeeks"

# Creating an instance of QRCode class
qr = qrcode.QRCode(version = 1,
                   box_size = 10,
                   border = 5)

# Adding data to the instance 'qr'
qr.add_data(data)

qr.make(fit = True)
img = qr.make_image(fill_color = 'red',
                    back_color = 'white')

img.save('MyQRCode2.png')
```

**输出:**

![](img/fdc32f2e820a1a9292b02a447336da3a.png)