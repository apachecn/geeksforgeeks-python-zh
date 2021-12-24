# 如何在 Python3 中复制文件？

> 原文:[https://www.geeksforgeeks.org/how-to-copy-file-in-python3/](https://www.geeksforgeeks.org/how-to-copy-file-in-python3/)

**先决条件** : [关闭](https://www.geeksforgeeks.org/python-shutil-copy2-method/#:~:text=Shutil%20module%20in%20Python%20provides,removal%20of%20files%20and%20directories.)

当我们需要数据备份时，我们通常会制作该文件的副本。Python 支持文件处理，允许用户处理文件，即读取和写入文件，以及许多其他文件处理选项，对文件进行操作。在这里，我们将学习如何使用 Python3 复制文件。

**方法 1:使用 shutil 库**

shutil 库包括一个方法调用 copyfile()。该方法采用两个参数，一个是文件的源路径，另一个是文件的目标路径。下图包含一个文件及其路径。

**语法:**

```
copyfile(source_path,destination_path)
```

![](img/e843e85fcab8ae3581c4354ca3d45227.png)

文件的源路径

**程序:**

## 蟒蛇 3

```
# copy a file using shutil.copyfile() method
import shutil

# path where original file is located
sourcePath = "c:\\SourceFolder\\gfg.txt"

# path were a copy of file is needed
destinationPath = "c:\\DestinationFolder\\gfgcopy.txt"

# call copyfile() method
shutil.copyfile(sourcePath, destinationPath)
```

**输出:**

![](img/930478de58e4c177842b5470355af9f7.png)

目标文件夹

**方法二:将文件的数据复制到另一个文件中**

将一个文件的数据复制到另一个文件也可以创建文件的备份。假设文件的数据如下:

![](img/7aff75a89288184c62890c0ebe0d1283.png)

源文件中的数据

**程序:**

## 蟒蛇 3

```
# open source file in read mode
source = open("c:\\SourceFolder\\gfg.txt", "r")

# open destination file in write mode
dest = open("c:\\DestinationFolder\\gfgcopy.txt", "w")

# read first line
line = source.readline()

# read lines until reached EOF
while line:

    # write line into destination file
    dest.write(line)
    # read another line
    line = source.readline()

# close both files
source.close()
dest.close()
```

**输出:**

![](img/c576885e72f67fb36d589479526549e1.png)

结果文件