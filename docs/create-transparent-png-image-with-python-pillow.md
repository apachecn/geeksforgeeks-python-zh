# 用 Python 创建透明 png 图像–枕头

> 原文:[https://www . geesforgeks . org/create-transparent-png-image-with-python-pillow/](https://www.geeksforgeeks.org/create-transparent-png-image-with-python-pillow/)

要使用 Python3 创建透明的 png，请使用枕头库。枕头库自带 python。如果 python 找不到枕头库，请打开命令提示符并运行以下命令:-

```py
pip install Pillow
```

**注意:**如果用 pip 安装 pipe 有问题，那就先安装设置 pip。为此查看[这篇](https://www.geeksforgeeks.org/how-to-install-pip-on-windows/)文章。

**进场:**

**1。从枕头库中导入图像模块**

```py
from PIL import Image
```

**2。打开任何图像并获取 RAGBAG 值。**

> img = Image.open('image.png ')。
> 
> rgba = img.convert("RGBA ")
> 
> data = rgba . get data()

**3。改变颜色**

数据将是一个成像核心对象，包含数千个 RGBA 值元组。要使背景透明，首先我们必须找到背景的 RGBA 值或任何我们想要使其透明的颜色。在这张图片中，背景颜色是黑色。

![](img/c6e1280efa13411c4fb7e256684cc0a1.png)

黑色的 RGB 值为(0，0，0)。现在我们将循环数据(RGBA 值)，每当我们发现一个黑色像素，我们将替换为一个透明的 RGBA 值，即(255，255，255，0)，其他颜色将保持不变。我们将这些值存储在一个名为 newData 的新列表中。

> 新数据= []
> 
> 对于数据中的项目:
> 
> 如果项[0] == 0 和项[1] == 0 和项[2] == 0:
> 
> new data . append(255、255、255、0)
> 
> 否则:
> 
> newData.append 项目

**4。存储更改后的图像**

将新数据存储为 RGBA 值，并将图像保存为 png 格式(透明图像不能存储为 jpeg 或 JPEG 格式)。

> rgba.putdata(新资料)
> 
> rgba . save(" transparent _ image . png "，" png ")

**实施:**

## 蟒蛇 3

```py
from PIL import Image

img = Image.open('image.png')
rgba = img.convert("RGBA")
datas = rgba.getdata()

newData = []
for item in datas:
    if item[0] == 0 and item[1] == 0 and item[2] == 0:  # finding black colour by its RGB value
        # storing a transparent value when we find a black colour
        newData.append((255, 255, 255, 0))
    else:
        newData.append(item)  # other colours remain unchanged

rgba.putdata(newData)
rgba.save("transparent_image.png", "PNG")
```

**输出:**

![](img/653afd8a0e33bb12b50091683ee875fa.png)

现在拍摄相同的图像，如果我们想使黄色透明，我们需要使黄色像素透明。为此，我们必须通过其 RBG 值(255，255，0)找到黄色，并将其替换为(255，255，255，0)。

新代码如下所示–

## 蟒蛇 3

```py
from PIL import Image

img = Image.open('image.png')
rgba = img.convert("RGBA")
datas = rgba.getdata()

newData = []
for item in datas:
    if item[0] == 255 and item[1] == 255 and item[2] == 0:  # finding yellow colour
        # replacing it with a transparent value
        newData.append((255, 255, 255, 0))
    else:
        newData.append(item)

rgba.putdata(newData)
rgba.save("transparent_image.png", "PNG")
```

**输出:**

![](img/90be2816ae2d2bf9301ec37d69b74a30.png)

这里我们把黄色变成透明的。