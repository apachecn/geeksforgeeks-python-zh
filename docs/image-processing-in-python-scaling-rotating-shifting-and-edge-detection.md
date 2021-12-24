# Python 中的图像处理(缩放、旋转、移位和边缘检测)

> 原文:[https://www . geeksforgeeks . org/python 中的图像处理-缩放-旋转-移位-边缘检测/](https://www.geeksforgeeks.org/image-processing-in-python-scaling-rotating-shifting-and-edge-detection/)

拍照只是点击的问题，所以为什么玩它应该不仅仅是几行代码。python 似乎不是这样。python 中有很多好的库可以用来处理图像，比如 open-cv、抱枕等。在本文中，我们将使用 [Open CV](https://opencv.org/) ，一个用于计算机视觉的开源库。它有 C++、python 和 java 接口。它针对计算机视觉领域的实时应用进行了高度优化(用 C/C++编写)。

让我们从一个简单的开始，即缩放图像。

**缩放图像** :-

缩放操作增加/减小图像的大小。

```py
import cv2
import numpy as np

FILE_NAME = 'volleyball.jpg'
try:
    # Read image from disk.
    img = cv2.imread(FILE_NAME)

    # Get number of pixel horizontally and vertically.
    (height, width) = img.shape[:2]

    # Specify the size of image along with interploation methods.
    # cv2.INTER_AREA is used for shrinking, whereas cv2.INTER_CUBIC
    # is used for zooming.
    res = cv2.resize(img, (int(width / 2), int(height / 2)), interpolation = cv2.INTER_CUBIC)

    # Write image back to disk.
    cv2.imwrite('result.jpg', res)

except IOError:
    print ('Error while reading files !!!')
```

**输出:**
![](img/3e8384598c3f3dfc09f500705635cfc6.png)

**旋转图像:-**
图像可以顺时针或逆时针旋转任意角度。我们只需要定义旋转矩阵，列出旋转点、旋转度和比例因子。

```py
import cv2
import numpy as np

FILE_NAME = 'volleyball.jpg'
try:
    # Read image from the disk.
    img = cv2.imread(FILE_NAME)

    # Shape of image in terms of pixels.
    (rows, cols) = img.shape[:2]

    # getRotationMatrix2D creates a matrix needed for transformation.
    # We want matrix for rotation w.r.t center to 45 degree without scaling.
    M = cv2.getRotationMatrix2D((cols / 2, rows / 2), 45, 1)
    res = cv2.warpAffine(img, M, (cols, rows))

    # Write image back to disk.
    cv2.imwrite('result.jpg', res)
except IOError:
    print ('Error while reading files !!!')
```

**输出:**
![](img/a0fa201f2f5ad2f4527dfb042d09fd59.png)

**翻译图像:-**
翻译图像意味着在给定的参照系内移动图像。

```py
import cv2
import numpy as np

FILE_NAME = 'volleyball.jpg'
# Create translation matrix.
# If the shift is (x, y) then matrix would be
# M = [1 0 x]
#     [0 1 y]
# Let's shift by (100, 50).
M = np.float32([[1, 0, 100], [0, 1, 50]])

try:

    # Read image from disk.
    img = cv2.imread(FILE_NAME)
    (rows, cols) = img.shape[:2]

    # warpAffine does appropriate shifting given the
    # translation matrix.
    res = cv2.warpAffine(img, M, (cols, rows))

    # Write image back to disk.
    cv2.imwrite('result.jpg', res)

except IOError:
    print ('Error while reading files !!!')
```

**输出:**
![](img/b35f700d8be82213755c98dc31c4e2bb.png)

**图像中的边缘检测:-**
图像检测的过程包括检测图像中的尖锐边缘。这种边缘检测在图像识别或[物体定位/检测](https://en.wikipedia.org/wiki/Object_detection)的环境中是必不可少的。由于其广泛的适用性，有多种边缘检测算法。我们将使用一种称为 [Canny 边缘检测](https://en.wikipedia.org/wiki/Canny_edge_detector)的算法。

```py
import cv2
import numpy as np

FILE_NAME = 'volleyball.jpg'
try:
    # Read image from disk.
    img = cv2.imread(FILE_NAME)

    # Canny edge detection.
    edges = cv2.Canny(img, 100, 200)

    # Write image back to disk.
    cv2.imwrite('result.jpg', edges)
except IOError:
    print ('Error while reading files !!!')
```

**输出:**
![](img/cefacc82caedd2a9fd3b6b893e178005.png)

详情请参考 [Github](https://github.com/ravi089/Image-Processing-Python) 。