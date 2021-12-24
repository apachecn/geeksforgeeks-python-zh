# 如何在 Python 中水平或垂直翻转图像？

> 原文:[https://www . geeksforgeeks . org/如何在 python 中水平或垂直翻转图像/](https://www.geeksforgeeks.org/how-to-flip-an-image-horizontally-or-vertically-in-python/)

**先决条件:**T2】PIL

给定一个图像，这里的任务是生成一个 Python 脚本来水平和垂直翻转图像。这里用于任务的模块是 PIL 和转置()函数的这个模块。

**语法:**

```
transpose(degree)
```

关键词 FLIP_TOP_BOTTOM 和 FLIP_LEFT_RIGHT 将传递给转置方法进行翻转。

*   翻转顶部底部–返回垂直翻转的原始图像
*   返回水平翻转的原始图像

### 方法

*   导入模块
*   打开原始图像
*   根据需要变换图像
*   保存新的转换图像。

**使用中的图像:**

![](img/d359f1ce142e6175ef71584ace621fa3.png)

**示例:**垂直翻转图像

## 蟒蛇 3

```
# importing PIL Module
from PIL import Image

# open the original image
original_img = Image.open("original.png")

# Flip the original image vertically
vertical_img = original_img.transpose(method=Image.FLIP_TOP_BOTTOM)
vertical_img.save("vertical.png")

# close all our files object
original_img.close()
vertical_img.close()
```

**输出:**

![](img/2ffe6b9de1615265521b1acf151d0111.png)

**示例:**水平翻转图像

## 蟒蛇 3

```
# importing PIL Module
from PIL import Image

# open the original image
original_img = Image.open("original.png")

# Flip the original image horizontally
horz_img = original_img.transpose(method=Image.FLIP_LEFT_RIGHT)
horz_img.save("horizontal.png")

# close all our files object
original_img.close()
horz_img.close()
```

**输出:**

![](img/c42d6042ab6cdcbc110e2dd12c1b6947.png)