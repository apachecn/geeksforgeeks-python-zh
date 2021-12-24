# Python–使用枕头的通道下降

> 原文:[https://www . geeksforgeeks . org/python-channel-drop-use-pizzle/](https://www.geeksforgeeks.org/python-channel-drop-using-pillow/)

通道丢弃是一种移除多通道图像通道之一的方法。通过*移除*意味着将特定通道的颜色值变为 0(所有像素)，即该特定通道对最终图像没有任何影响(假设颜色“正常”混合)。删除颜色通道时，会遵循颜色理论(色轮)。一旦删除了一个通道，就会添加其他通道的值来创建新图像。这种方法广泛用于图像处理软件包，如 Adobe Photoshop、Gimp 等。

我们将使用`pillow`库来实现通道丢弃。要安装库，请在命令行中执行以下命令:

```
pip install pillow

```

在后面的一个方法中，我们将利用 numpy 库提供的 elementwise 操作。要安装`numpy`，请在命令行中执行以下命令:

```
pip install numpy

```

**方法 1:**

在这个方法中，我们将使用传递给`Image.convert()`的变换矩阵作为参数。变换矩阵是:

```
newRed   = 1*oldRed  +  0*oldGreen  +  0*oldBlue  + constant
newGreen = 0*oldRed  +  1*OldGreen  +  0*OldBlue  + constant
newBlue  = 0*oldRed  +  0*OldGreen  +  1*OldBlue  + constant

```

正常的 RGB 图像将具有如上所示的矩阵。

```
(1, 0, 0, 0,
 0, 1, 0, 0,
 0, 0, 1, 0)

```

在上面的矩阵中，将 1 更改为 0 将删除该特定通道。出于我们的目的，我们不需要改变其他偏移的值，因为它们会导致不同的效果，这是不需要的。

**样本图像:**

![Sample Image (Copyright Free)](img/eac70654fc5ffed1c1d5ef79347c29a5.png)

**代码:**

```
from PIL import Image

# Creating a image object, of the sample image
img = Image.open(r'sample.jpg')

# A 12-value tuple which is a transform matrix for dropping 
# green channel (in this case)
matrix = ( 1, 0, 0, 0,
           0, 0, 0, 0,
           0, 0, 1, 0)

# Transforming the image to RGB using the aforementioned matrix 
img = img.convert("RGB", matrix)

# Displaying the image 
img.show()
```

**输出图像:**

![Dropped Green Channel](img/64d62d37b7f25e9059aa1194eab40de9.png)

**解释:**

首先，我们通过使用`Image.open()`打开图像来创建图像对象，然后将返回的对象保存在变量`img`中。然后我们用值填充我们的变换矩阵(`matrix`变量)，这将导致绿色通道从图像中移除。由于绿色通道从图像中移除(无效)
最终图像的像素值取决于图像的红色和蓝色通道(给出洋红色的阴影，因为红色+蓝色=洋红色)。然后我们将变换矩阵发送到`convert()`方法并保存返回的图像。最后，我们使用`img.show()`显示图像。

通过将几个 1 更改为 0，同样的效果可以应用于多个通道。

**示例:**

相同的代码，但矩阵:

```
matrix = ( 0, 0, 0, 0,
           0, 0, 0, 0,
           0, 0, 1, 0)

```

会产生图像

![Dropped Red And Green Channels](img/953270d51b62d1713c2b18d244f1b286.png)

这是红色和绿色通道被丢弃的图像(因为它们的位置值是 0)。因此合成的图像是蓝色的。

与矩阵相同的代码:

```
matrix = ( 1, 0, 0, 0,
           0, 1, 0, 0,
           0, 0, 1, 0)

```

会产生图像

![Sample Image (Copyright Free)](img/eac70654fc5ffed1c1d5ef79347c29a5.png)

这是原始图像，因为所有位置值都是 1，因此保留了所有颜色通道。

**方法 2:**

在这种方法中，我们将使用 numpy 库提供的 elementiwise 乘法运算(在我们的例子中是广播)，来否定图像的颜色通道。

**代码:**

```
from PIL import Image
import numpy as np

# Opening the test image and saving its object
img = Image.open(r'sample.jpg')

# Creating an array out of pixel values of the image
img_arr = np.array(img, np.uint8)

# Setting the value of every pixel in the 3rd channel to 0
# Change the 2 to 1 if wanting to drop the green channel 
# Change the 2 to 0 if wanting to drop the red channel
img_arr[::, ::, 2] = 0

# Creating an image from the modified array
img = Image.fromarray(img_arr)

# Displaying the image
img.show()
```

**输出图像:**

![Blue Channel Dropped](img/74e7341ac4fae12bd567410b8919772d.png)

**解释:**

首先，我们为样本图像获取一个图像对象，并将其存储在变量`img`中。然后，我们使用带有数据类型`np.uint8` (8 位无符号整数)的函数`np.array()`将图像转换为 numpy 数组。之后，我们使用`img_arr[::, ::, 2] = 0`将 0 指定为蓝色通道中每个像素的值，这意味着给该多通道矩阵的第三通道(蓝色)的每一行和每一列一个 0 值。然后我们用这个数组用`Image.fromarray()`创建一个新的图像。最后，我们展示了图像。

**注:**第三个参数中的 **2** 被视为蓝色通道(第三个通道)的原因是 numpy 使用基于 0 的索引，因此第一个元素位于索引 0，而不是 1，从而使索引 2 中的元素成为第三个元素。