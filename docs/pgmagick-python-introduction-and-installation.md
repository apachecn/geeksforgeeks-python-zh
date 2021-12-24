# pgmagick Python-介绍和安装

> 原文:[https://www . geesforgeks . org/pgmagick-python-introduction-and-installation/](https://www.geeksforgeeks.org/pgmagick-python-introduction-and-installation/)

**pgmagick** 是 Python 的 GraphicsMagick 绑定。本模块提供图像编辑和操作的方法。《pgmagick》是由 Hideo 服部哲写的。
我们可以用这个库做很多事情，比如:

***   Resize, rotate, sharpen, color restore, or add special effects to the image.*   Create transparent image assets.*   Compare the two pictures.*   Create a gradient image.*   Draw text.*   Draw the text of 2-byte code.*   Get image size*   Edge extraction*   Create GIF animation with images.*   Add a frame to the image.*   Convert an image from one format to another.**

**安装:**
安装 **pgmagick** 有两种方式:

1.  **窗口:**在命令提示符下执行以下命令-

    ```
    pip install pgmagick

    ```

2.  **乌班图:**在终端执行以下命令-

    ```
    ### Ubuntu11.10+ ###
    $ apt-get install python-pgmagick

    ### Ubuntu10.04+ ###
    $ apt-get install libgraphicsmagick++1-dev
    $ apt-get install libboost-python1.40-dev

    ```

**示例#1:** 让我们讨论一个调整图像大小的代码-

为了便于说明，我拍摄了以下示例图像-
![](img/72660985dcd8be07afbe3e5a743e83dd.png)

```
from pgmagick import Image

#Include full path to the input image
img = Image('input_image.jpg')  
img.filterType(FilterTypes.SincFilter)
img.resize('150x150')
img.write('output_image.jpg')
```

**输出:**
![](img/6b615c2b2cee397058eb842cde1aad87.png)

**示例#2:** 让我们讨论一个缩放图像的代码-
我使用了与上述示例相同的样本图像作为输入。

```
from pgmagick import Image

#Include full path to the input image
img = Image('input_image.jpg') 
img.quality(100)
img.scale('100x100')
img.sharpen(1.0)
img.write('output_image.jpg')
```

如果您尝试在最后运行代码，您将看到图像按照新的维度成功地重新采样，并且您将获得一个新的图像。

**参考文献:**

1.  https://pypi.org/project/pgmagick/
2.  https://pythonhosted.org/pgmagick/#license
3.  https://pythonhosted.org/pgmagick/cookbook.html#