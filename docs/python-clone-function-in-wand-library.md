# Python–在魔杖库中克隆()函数

> 原文:[https://www . geesforgeks . org/python-clone-function-in-wand-library/](https://www.geeksforgeeks.org/python-clone-function-in-wand-library/)

`clone()`功能制作原始图像的精确副本。可以使用该克隆图像进行操作，而不影响原始图像。clone()是最重要的功能之一，因为它有助于安全地操作图像。

例如，如果你得到一个图像，你把原始文件搞砸了，这可能会给一个人带来巨大的损失。但是使用 clone()函数可以避免这个问题。在图像中执行操作之前，可以创建图像的精确副本，并操作原始文件的副本。

**语法:**

```
original = Image(filename='filename.format')
copy = original.clone()
// other manipulation code

```

或者

```
with Image(filename='filename.format') as original:
    with original.clone() as copy:
         // other image manipulation code

```

**代码:**

让我们编写一个代码来克隆一个映像，然后更改克隆映像的格式。

```
# import Image from wand.image module
from wand.image import Image

# read original file using Image() function
with Image(filename ='koala.jpg') as original:

    # creating clone image of original image
    with original.clone() as copy:

        # convert format of cloned image
        converted.format = 'png'
```

**输出:**

```
A copy image will be saved with png extension/format
```