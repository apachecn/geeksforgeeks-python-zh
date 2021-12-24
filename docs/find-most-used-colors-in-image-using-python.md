# 使用 Python 找到图像中最常用的颜色

> 原文:[https://www . geesforgeks . org/find-最常用的图像颜色-使用 python/](https://www.geeksforgeeks.org/find-most-used-colors-in-image-using-python/)

**先决条件:**T2PILT5】

PIL 是 python 图像库，它为 Python 解释器提供图像编辑功能。它是由弗雷德里克·伦德和其他几位贡献者开发的。枕头是友好的 PIL 叉子和一个易于使用的图书馆，由亚历克斯·克拉克和其他贡献者开发。我们将和枕头一起工作。

**让我们用分步实现来理解:**

**1。**读取图像

读取 PIL 的图像，我们使用**图像**方法。

```py
# Read an Image
img = Image.open('File Name')
```

**2。**转换为 RGB 图像

```py
img.convert('RGB')
```

**3。**获取图像的宽度和高度

```py
width, height = img.size
```

**4。**迭代图像的所有像素，并从该像素获得 **R，G，B** 值

```py
for x in range(0, width):
    for y in range(0, height):
        r, g, b = img.getpixel((x,y))
        print(img.getpixel((x,y)))
```

**输出:**

> (155, 173, 151), (155, 173, 151), (155, 173, 151), (155, 173, 151), (155, 173, 151) …

**5。**初始化三个变量

*   r_total = 0
*   g_total = 0
*   b_total = 0

遍历所有像素，并将每种颜色添加到不同的初始化变量中。

```py
r_total = 0
g_total = 0
b_total = 0

for x in range(0, width):
    for y in range(0, height):
        r, g, b = img.getpixel((x,y))
        r_total += r
        g_total += g
        b_total += b
print(r_total, g_total, b_total)
```

**输出:**

```py
(29821623, 32659007, 33290689)
```

由于我们可以 R，G & B 值非常大，这里我们将使用计数变量

**再初始化一个变量**

计数= 0

```py
Divide total color value by count
```

**下面是实现:**

**使用的图像–**

![](img/3050d2da0588bd3ee353be44068e6602.png)

## 蟒蛇 3

```py
# Import Module
from PIL import Image

def most_common_used_color(img):
    # Get width and height of Image
    width, height = img.size

    # Initialize Variable
    r_total = 0
    g_total = 0
    b_total = 0

    count = 0

    # Iterate through each pixel
    for x in range(0, width):
        for y in range(0, height):
            # r,g,b value of pixel
            r, g, b = img.getpixel((x, y))

            r_total += r
            g_total += g
            b_total += b
            count += 1

    return (r_total/count, g_total/count, b_total/count)

# Read Image
img = Image.open(r'C:\Users\HP\Desktop\New folder\mix_color.png')

# Convert Image into RGB
img = img.convert('RGB')

# call function
common_color = most_common_used_color(img)

print(common_color)
# Output is (R, G, B)
```

**输出:**

```py
# Most Used color is Blue
(179.6483313253012, 196.74100602409638, 200.54631927710844)
```