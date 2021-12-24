# 在 Python 中寻找图像的尺寸分辨率

> 原文:[https://www . geesforgeks . org/find-大小-分辨率-python 中的图像/](https://www.geeksforgeeks.org/finding-the-size-resolution-of-image-in-python/)

让我们看看如何在 Python 中找到图像的分辨率。我们将用 Python 中的两个不同的库来解决这个问题:

*   PIL
*   OpenCV

在我们的示例中，我们将使用以下图像:

![](img/31cccbc738458212a3ba180fe1c85f63.png)

上图分辨率为 600×135。

### 利用 PIL

我们将使用一个名为枕头的库来查找图像的大小(分辨率)。我们将使用功能 **PIL。Image.open()** 打开并读取我们的图像，并使用功能 **img.size** 将尺寸存储在两个变量中。

## 蟒蛇 3

```
# importing the module
import PIL
from PIL import Image

# loading the image
img = PIL.Image.open("geeksforgeeks.png")

# fetching the dimensions
wid, hgt = img.size

# displaying the dimensions
print(str(wid) + "x" + str(hgt))
```

**输出:**

```
600x135

```

### 使用 OpenCV

我们将通过导入库 **cv2** 来导入 OpenCV。我们将使用 **cv2.imread()** 功能加载图像。之后，可以使用**形状**属性找到尺寸。**形状【0】**会给我们高度，**形状【1】**会给我们宽度。

## 蟒蛇 3

```
# importing the module
import cv2

# loading the image
img = cv2.imread("geeksforgeeks.png")

# fetching the dimensions
wid = img.shape[1]
hgt = img.shape[0]

# displaying the dimensions
print(str(wid) + "x" + str(hgt))
```

**输出:**

```
600x135

```