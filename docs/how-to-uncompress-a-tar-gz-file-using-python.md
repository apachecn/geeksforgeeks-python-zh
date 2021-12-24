# 如何用 Python 解压一个“. tar.gz”文件？

> 原文:[https://www . geesforgeks . org/如何使用 python 解压缩-a-tar-gz-file/](https://www.geeksforgeeks.org/how-to-uncompress-a-tar-gz-file-using-python/)

. tar.gz 文件是由 tar 打包和一个 GNU zip (gzip)压缩组合而成的。这些文件通常在基于 Unix/Linux 的系统中作为包或安装程序使用。为了读取或提取这些文件，我们必须首先解压缩这些文件，然后使用 TAR 实用程序扩展它们，因为这些文件包含这两者。焦油和。gz 文件。

为了使用 python 提取或解压缩“. tar.gz”文件，我们必须使用 python 中的 tarfile 模块。这个模块可以读写。焦油文件包括。gz，。bz 压缩方法。

### 方法

*   导入模块
*   打开. tar.gz 文件
*   提取特定文件夹中的文件
*   关闭文件

### **正在使用的文件**

**名称:** gfg.tar.gz

**链接下载此文件:** [点击此处](https://drive.google.com/file/d/1rhxY2pRpdSzjP75lAzP_zsn3P0wJMc5S/view?usp=sharing)

**内容:**

![](img/68913664a31912e8c502a05cf85c0edb.png)

“gfg.tar.gz”文件

**示例:**

## 蟒蛇 3

```py
# importing the "tarfile" module
import tarfile

# open file
file = tarfile.open('gfg.tar.gz')

# extracting file
file.extractall('./Destination_FolderName')

file.close()
```

**输出:**

![](img/ae0dbf51f599e575cbd550b03a4a501b.png)

将创建一个名为“目标文件夹”的文件夹。

![](img/52cd1f8fb4eac80c64f5ba02ff9b209c.png)

文件在“目标文件夹”中解压缩

**示例:**提取前打印文件名

## 蟒蛇 3

```py
# importing the "tarfile" module
import tarfile

# open file
file = tarfile.open('gfg.tar.gz')

# print file names
print(file.getnames())

# extract files
file.extractall('./Destination_FolderName')

# close file
file.close()
```

**输出:**

![](img/454a6e7fe0e2c3231e1de196175bc1a5.png)

**示例:**提取特定文件

## 蟒蛇 3

```py
# importing the "tarfile" module
import tarfile

# open file
file = tarfile.open('gfg.tar.gz')

# extracting a specific file
file.extract('sample.txt', './Destination_FolderName')

file.close()
```

**输出:**

![](img/418e1cf9eb28853b08f5a5d93862a486.png)

将创建一个名为“目标文件夹名”的新文件夹

![](img/abd211c5285180f5790f7d182db7bb26.png)

“sample.txt”在“Destination_FolderName”中未压缩