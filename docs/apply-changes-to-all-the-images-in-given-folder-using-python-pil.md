# 将更改应用到给定文件夹中的所有图像–使用 Python PIL

> 原文:[https://www . geesforgeks . org/apply-changes-to-all-the-images-in-folder-using-python-pil/](https://www.geeksforgeeks.org/apply-changes-to-all-the-images-in-given-folder-using-python-pil/)

给定一个原始图像数据集，通常需要一些预处理，这是一个人必须做的事情。这通常是一项需要对每个图像执行一些重复操作的任务。嗯，我们可以使用一些简单的 Python 代码和一些库来轻松地自动化这个过程。因此，在没有进一步告别的情况下，让我们看看如何将更改应用到给定文件夹中的所有图像，并使用 Python PIL 将其保存到某个目标文件夹中。

让我们安装所有必需的模块–

```py
pip3 install pillow
pip3 install os-sys
```

我们将解析文件夹中的所有图像，以便同时对它们进行更改/操作。

```py
# Code to apply operations on all the images
# present in a folder one by one
# operations such as rotating, cropping, 
from PIL import Image
from PIL import ImageFilter
import os

def main():
    # path of the folder containing the raw images
    inPath ="E:\\GeeksforGeeks\\images"

    # path of the folder that will contain the modified image
    outPath ="E:\\GeeksforGeeks\\images_rotated"

    for imagePath in os.listdir(inPath):
        # imagePath contains name of the image 
        inputPath = os.path.join(inPath, imagePath)

        # inputPath contains the full directory name
        img = Image.open(inputPath)

        fullOutPath = os.path.join(outPath, 'invert_'+imagePath)
        # fullOutPath contains the path of the output
        # image that needs to be generated
        img.rotate(90).save(fullOutPath)

        print(fullOutPath)

# Driver Function
if __name__ == '__main__':
    main()
```

文件夹中的示例图像–

**输入:**

**![](img/df5af375976c58eb7f9d40112eed4632.png)

image _ sample 1** 
**输出:![](img/83fd4d05766f252663475825acdd080d.png)

invert _ image _ sample 1**