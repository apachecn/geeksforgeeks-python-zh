# 在 Python 中将图像转换为 ASCII 图像

> 原文:[https://www . geesforgeks . org/converting-image-ascii-image-python/](https://www.geeksforgeeks.org/converting-image-ascii-image-python/)

**ASCII 艺术简介**

ASCII 艺术是一种图形设计技术，使用计算机进行演示，由 95 个可打印字符(总共 128 个)拼凑而成的图片组成，这些字符由 1963 年的 ASCII 标准和具有专有扩展字符的 ASCII 兼容字符集(超过标准 7 位 ASCII 的 128 个字符)定义。该术语通常也用来泛指基于文本的视觉艺术。ASCII 艺术可以用任何文本编辑器创建，并且经常用于自由格式的语言。ASCII 艺术的大多数例子需要固定宽度的字体(非比例字体，如在传统的打字机上)如 Courier 用于演示。已知的 ASCII 艺术中最古老的例子是计算机艺术先驱肯尼斯·诺尔顿在 1966 年左右的创作，他当时在贝尔实验室工作。肯·诺尔顿(Ken Knowlton)和利昂·哈蒙(Leon Harmon)1966 年的《感知研究 I》展示了他们早期 ASCII 艺术的一些例子。ASCII 艺术的发明，很大程度上是因为早期的印刷者往往缺乏图形能力，因此字符被用来代替图形标记。此外，为了标记来自不同用户的不同打印作业之间的划分，批量打印机通常使用 ASCII 艺术来打印大横幅，使划分更容易被发现，以便计算机操作员或职员更容易分离结果。当图像不能嵌入时，ASCII 艺术也被用在早期的电子邮件中。你可以找到更多关于他们的信息。【来源:[维基](https://en.wikipedia.org/wiki/ASCII_art)。

**工作原理:**

以下是程序生成 ASCII
图像的步骤:

*   将输入图像转换为灰度。
*   将图像分割成 M×N 块。
*   校正 M(行数)以匹配图像和字体的纵横比。
*   计算每个图像块的平均亮度，然后为每个图像块查找合适的 ASCII 字符。
*   将一行行 ASCII 字符串组合在一起，并将其打印到一个文件中，以形成最终图像。

**要求**

你用 python 做这个程序，我们将使用[枕头](https://python-pillow.org/)，这是 Python 图像库，用于读入图像，访问它们的底层数据，并创建和修改它们，还有科学模块 [Numpy](http://www.numpy.org/) 来计算平均值。

**代码**
首先，您将定义用于生成 ASCII 艺术的灰度级别。然后，您将了解如何将图像分割成图块，以及如何计算这些图块的平均亮度。接下来，您将使用 ASCII 字符替换切片，以生成最终输出。最后，您将为程序设置命令行解析，以允许用户指定输出大小、输出文件名等。

**定义灰度等级和网格**

作为创建程序的第一步，定义用于将亮度值转换为 ASCII 字符的两个灰度级别作为全局值。

```
>>>gscale1 = "$@B%8&WM#*oahkbdpqwmZO0QLCJUYXzcvunxrjft/\|()1{}[]?-_+~i!lI;:,\"^`". "    #70 levels of gray
>>>gscale2 = "@%#*+=-:. "         #10 levels of gray
```

u 处的 gscale1 值是 70 级灰度斜坡，v 处的 gscale2 值是更简单的 10 级灰度斜坡。这两个值都存储为字符串，字符范围从最暗到最亮。
现在您已经有了灰度渐变，可以设置图像了。以下代码打开图像并将其分割成网格:

```
    # open image and convert to grayscale
>>>    image = Image.open(fileName).convert('L')
    # store dimensions
>>>    W, H = image.size[0], image.size[1]
    # compute width of tile
>>>    w = W/cols
    # compute tile height based on aspect ratio and scale
>>>    h = w/scale
    # compute number of rows
>>>    rows = int(H/h)
```

**计算平均亮度**
接下来，计算灰度图像中一个图块的平均亮度。函数 getAverageL()可以完成这项工作。

```
#Given PIL Image, return average value of grayscale value
>>>def getAverageL(image):
    # get image as numpy array
...    im = np.array(image)
    # get shape
...    w,h = im.shape
    # get average
...    return np.average(im.reshape(w*h))
```

首先，图像块作为 PIL 图像对象传入。在第二步将图像转换为 numpy 数组，此时“im”成为每个像素的二维亮度数组。第三步，存储图像的尺寸(宽度和高度)。第四步，numpy.average()计算图像中亮度值的平均值，方法是使用 numpy.reshape()首先将二维数组的宽度和高度(w，h)转换为？一维数组的长度是宽度乘以高度(w*h)的乘积。numpy.average()调用然后对这些数组值求和并计算平均值。

**从图像生成 ASCII 内容**

```
    # ascii image is a list of character strings
>>>    aimg = []
    # generate list of dimensions
>>>    for j in range(rows):
...        y1 = int(j*h)
...        y2 = int((j+1)*h)
        # correct last tile
...        if j == rows-1:
...            y2 = H
        # append an empty string
...        aimg.append("")
...        for i in range(cols):
            # crop image to tile
...            x1 = int(i*w)
...            x2 = int((i+1)*w)
            # correct last tile
...            if i == cols-1:
...                x2 = W
            # crop image to extract tile
...            img = image.crop((x1, y1, x2, y2))
            # get average luminance
...            avg = int(getAverageL(img))
            # look up ascii char
...            if moreLevels:
...                gsval = gscale1[int((avg*69)/255)]
...            else:
...                gsval = gscale2[int((avg*9)/255)]
            # append ascii char to string
...            aimg[j] += gsval
```

在程序的这一部分，ASCII 图像首先存储为字符串列表，在第一步初始化。接下来，迭代计算出的行图像切片数，在第二步和下一行，计算每个图像切片的起始和结束 y 坐标。虽然这些都是？浮点计算，在将它们传递给图像裁剪方法之前将其截断为整数。接下来，因为将图像分割成小块只会在图像宽度是列数的整数倍时创建相同大小的边缘小块，所以请通过将 y 坐标设置为图像的实际高度来校正最后一行中小块的 y 坐标。这样做可以确保图像的上边缘不会被截断。在第三步，您将一个空字符串添加到 ASCII 中，作为表示当前图像行的一种简洁方式。接下来你要填写这个字符串。(您将字符串视为字符列表。)在第四步和下一行，您计算每个图块的左右 x 坐标，在第五步，您纠正最后一个图块的 x 坐标，原因与纠正 y 坐标的原因相同。在第六步使用 image.crop()提取图像切片，然后将该切片传递给上面定义的 getAverageL()函数，将平均亮度值从[0，255]缩小到[0，9](默认 10 级灰度渐变的值范围)。然后使用 gscale2(存储的斜坡字符串)作为 ASCII Art 95 相关 ASCII 值的查找表。第八步中的行是相似的，除了它只在命令行？ag 设置为使用 70 级斜坡。最后，在最后一步，您将查找到的 ASCII 值 gsval 追加到文本行中，代码循环直到所有行都被处理完。
**添加命令行界面并将 ASCII 艺术字符串写入文本文件**
要添加命令行界面，请使用 python 内置模块 [argparse](https://docs.python.org/3/howto/argparse.html) 。
现在最后，获取生成的 ASCII 字符串列表，并将这些字符串写入文本文件。

```
# open a new text file
>>> f = open(outFile, 'w')
# write each string in the list to the new file
>>> for row in aimg:
...    f.write(row + '\n')
# clean up
>>> f.close()
```

然后添加这些部分来创建您的程序。完整的代码如下。

## 计算机编程语言

```
# Python code to convert an image to ASCII image.
import sys, random, argparse
import numpy as np
import math

from PIL import Image

# gray scale level values from:
# http://paulbourke.net/dataformats/asciiart/

# 70 levels of gray
gscale1 = "$@B%8&WM#*oahkbdpqwmZO0QLCJUYXzcvunxrjft/\|()1{}[]?-_+~<>i!lI;:,\"^`'. "

# 10 levels of gray
gscale2 = '@%#*+=-:. '

def getAverageL(image):

    """
    Given PIL Image, return average value of grayscale value
    """
    # get image as numpy array
    im = np.array(image)

    # get shape
    w,h = im.shape

    # get average
    return np.average(im.reshape(w*h))

def covertImageToAscii(fileName, cols, scale, moreLevels):
    """
    Given Image and dims (rows, cols) returns an m*n list of Images
    """
    # declare globals
    global gscale1, gscale2

    # open image and convert to grayscale
    image = Image.open(fileName).convert('L')

    # store dimensions
    W, H = image.size[0], image.size[1]
    print("input image dims: %d x %d" % (W, H))

    # compute width of tile
    w = W/cols

    # compute tile height based on aspect ratio and scale
    h = w/scale

    # compute number of rows
    rows = int(H/h)

    print("cols: %d, rows: %d" % (cols, rows))
    print("tile dims: %d x %d" % (w, h))

    # check if image size is too small
    if cols > W or rows > H:
        print("Image too small for specified cols!")
        exit(0)

    # ascii image is a list of character strings
    aimg = []
    # generate list of dimensions
    for j in range(rows):
        y1 = int(j*h)
        y2 = int((j+1)*h)

        # correct last tile
        if j == rows-1:
            y2 = H

        # append an empty string
        aimg.append("")

        for i in range(cols):

            # crop image to tile
            x1 = int(i*w)
            x2 = int((i+1)*w)

            # correct last tile
            if i == cols-1:
                x2 = W

            # crop image to extract tile
            img = image.crop((x1, y1, x2, y2))

            # get average luminance
            avg = int(getAverageL(img))

            # look up ascii char
            if moreLevels:
                gsval = gscale1[int((avg*69)/255)]
            else:
                gsval = gscale2[int((avg*9)/255)]

            # append ascii char to string
            aimg[j] += gsval

    # return txt image
    return aimg

# main() function
def main():
    # create parser
    descStr = "This program converts an image into ASCII art."
    parser = argparse.ArgumentParser(description=descStr)
    # add expected arguments
    parser.add_argument('--file', dest='imgFile', required=True)
    parser.add_argument('--scale', dest='scale', required=False)
    parser.add_argument('--out', dest='outFile', required=False)
    parser.add_argument('--cols', dest='cols', required=False)
    parser.add_argument('--morelevels',dest='moreLevels',action='store_true')

    # parse args
    args = parser.parse_args()

    imgFile = args.imgFile

    # set output file
    outFile = 'out.txt'
    if args.outFile:
        outFile = args.outFile

    # set scale default as 0.43 which suits
    # a Courier font
    scale = 0.43
    if args.scale:
        scale = float(args.scale)

    # set cols
    cols = 80
    if args.cols:
        cols = int(args.cols)

    print('generating ASCII art...')
    # convert image to ascii txt
    aimg = covertImageToAscii(imgFile, cols, scale, args.moreLevels)

    # open file
    f = open(outFile, 'w')

    # write to file
    for row in aimg:
        f.write(row + '\n')

    # cleanup
    f.close()
    print("ASCII art written to %s" % outFile)

# call main
if __name__ == '__main__':
    main()
```

输入:

```
$python "ASCII_IMAGE_GENERATOR.py" --file data/11.jpg --cols 120
```

**资源**T2【1】。[维基百科:ASCII _ ART](https://en.wikipedia.org/wiki/ASCII_art)T5】2。Python 游乐场:好奇程序员的极客项目。
3。[灰度等级值](http://paulbourke.net/dataformats/asciiart/)
4。[本文 Github 代码](https://github.com/electronut/pp/blob/master/ascii/ascii.py)
本文由 [**Subhajit Saha**](https://www.linkedin.com/in/subhajit-saha-06aa29131/) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。