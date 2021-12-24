# 在 Python 中基于大小属性过滤图像

> 原文:[https://www . geesforgeks . org/filling-images-based-size-attributes-python/](https://www.geeksforgeeks.org/filtering-images-based-size-attributes-python/)

先决条件:[PIL _ 工作-图像-python](https://www.geeksforgeeks.org/working-images-python/)

给定一个图像目录，我们的程序将根据给定的阈值大小创建一个新的图像目录。

一个简单的 Python3 函数，输入 Python 文件的路径、以像素为单位的阈值宽度和以像素为单位的阈值高度，搜索该唯一目录中的所有图像，并创建一个新目录，根据给定的阈值大小过滤掉所有图像，或者将其大小调整为给定的阈值宽度和高度。

> **后续步骤:**
> 
> 1.安装必要的库，如 PIL
> 2。导入库:PIL、shutil、os、os.path
> 3。将代码保存为尺寸过滤器. py
> 4。打开终端(python 文件存在并运行的地方)- > python sizeFilter.py

下面是上述方法的 Python3 实现:

```py
# Python3 program to Filtering Images
# based on Size Attributes 
from PIL import Image
from shutil import copyfile
import os, os.path

def filterImages(path, thresholdWidth, thresholdHeight):

    # Defining images array for
    # identifying only image files
    imgs = []

    # List of possible images extensions
    # add if you want more
    valid_images = [".jpg", ".gif", ".png", ".tga",
                    ".jpeg", ".PNG", ".JPG", ".JPEG"]

    # Storing all images in images array (imgs)
    for f in os.listdir(path):
        ext = os.path.splitext(f)[1]

        if ext.lower() not in valid_images:
            continue
        imgs.append(f)

    # Checking whether the filteredImages
    # directory exists or not
    directory = os.path.dirname('filteredImages' + path)
    if not os.path.exists(directory):
        os.makedirs(directory)

    # Defining filteredIMages array for
    # storing all the images we need
    filteredImages = []

    for i in imgs:
        image = Image.open(os.path.join(path, i))

        # Storing width and height of a image
        width, height = image.size

        # if only width exceeds the thresholdWidth
        if (width > thresholdWidth and
            height <= thresholdHeight):

            image.resize((thresholdWidth, 
                        (thresholdWidth * height)
                                // width)).save(i)

        # if only height exceeds the thresholdHeight
        elif (width <= thresholdWidth and
              height > thresholdHeight):

            image.resize(((thresholdHeight * width)
                        // height, thresholdHeight)).save(i)

        # if both the paramateres exceeds
        # the threshold attributes
        elif (width > thresholdWidth and
              height > thresholdHeight):

            image.resize((thresholdWidth, thresholdHeight)).save(i)

        copyfile(os.path.join(path, i),
                 os.path.join(path + '/filteredImages', i))

        filteredImages.append(i)

    # returning the filteredImages array
    return filteredImages

# Driver Code
if __name__ == '__main__':

    filteredImages = []

    # Enter the path of the python sizeFilter
    # file, the thresholdWidth(in pixels) and
    # thresholdHeight(in pixels)
    filteredImages = filterImages("/home/SahilKhosla/Desktop/Current Project", 1000, 1000)
```

输出:
<video controls=""><source src="https://media.geeksforgeeks.org/wp-content/uploads/sizeFilter-2.mp4" type="video/mp4"></video>