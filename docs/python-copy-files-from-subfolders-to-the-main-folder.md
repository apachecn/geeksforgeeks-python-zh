# Python–将文件从子文件夹复制到主文件夹

> 原文:[https://www . geesforgeks . org/python-将文件从子文件夹复制到主文件夹/](https://www.geeksforgeeks.org/python-copy-files-from-subfolders-to-the-main-folder/)

在本文中，我们将讨论如何将文件从子文件夹复制到主文件夹。本文中用于解释的目录树如下所示:

```py
D:\projects\base
|
|__subfolder:
|    \__file.txt
|      
|__main.py
| 
```

![](img/f201069f6decde223ec13bc631b30004.png)

这里我们有一个名为“base”的文件夹，其中有一个名为“subfile”的文件夹，它包含一个文件名 file.txt。

Python 附带了各种模块，这些模块提供了执行输入/输出操作的各种方法，我们将在这里讨论它们。

我们将讨论的各种方法包括

1.  **使用 shutil.copyfile()**
2.  **使用 shutil.copy()**
3.  **使用 shutil.copy2()**
4.  **使用 shutil.copyfileobj()**

### 方法 1:使用 shutil.copyfile()

使用 [shutil](https://www.geeksforgeeks.org/shutil-module-in-python/) 库的 [copyfile()](https://www.geeksforgeeks.org/python-shutil-copyfile-method/) 方法，我们可以轻松地将文件从一个位置复制到另一个位置。它有两个参数:需要复制的文件所在的源路径和需要复制文件的目标路径。下面是实现该方法的代码:

## 计算机编程语言

```py
# importing the shutil module
import shutil

# storing the current path of file.txt
# in the source variable
source = 'D:/projects/base/subfolder/file.txt'

# storing the destination path in the
# destination variable
destination = 'D:/projects/base/file.txt'

# calling the shutil.copyfile() method
shutil.copyfile(source,destination)
```

运行此代码后，我们会注意到名为 file.txt 的文件已被复制到基本文件夹。

![](img/f08bb658ca2766bf828249e4bb5c7e55.png)

shutil.copyfile()方法需要注意的几点:-

*   目标位置必须是可写的，否则将引发 IOError 异常。
*   如果目标已经存在，它将被替换。
*   不能使用此功能复制特殊文件，如字符或块设备和管道。
*   它不复制元数据。

### 方法 2:使用 shutil.copy()

使用 [shutil.copy()](https://www.geeksforgeeks.org/python-shutil-copy-method/) 方法我们也可以复制文件，唯一的语法变化是我们传递的目标字符串也可以是目录而不是完整的文件路径。例如，请参见下面的代码:

## 计算机编程语言

```py
# importing the shutil module
import shutil

# storing the current file path of file.txt
# in the source variable
source = 'D:/projects/base/subfolder/file.txt'

# storing the destination directory in the
# destination variable
destination = 'D:/projects/base'

# calling the shutil.copy() method
shutil.copy(source,destination)
```

运行此代码后，我们会注意到名为 file.txt 的文件已被复制到基本文件夹。

![](img/f08bb658ca2766bf828249e4bb5c7e55.png)

copyfile()和 copy()方法的主要区别是:

*   copy()方法也复制有关权限的信息，但 copyfile()方法不复制。
*   在 copy()方法中，目标字符串可以是目录或完整文件路径，但在 copyfile()方法中，它应该是完整文件路径。

### 方法 3:使用 shutil.copy2()

[shutil.copy2()](https://www.geeksforgeeks.org/python-shutil-copy2-method/) 方法也类似于 [shutil.copy()](https://www.geeksforgeeks.org/python-shutil-copy-method/) 方法，但是它做的额外的事情是它像时间戳一样复制元数据。
代码将与上面类似:

## 计算机编程语言

```py
# importing the shutil module
import shutil

# storing the current path of file.txt
# in the source variable
source = 'D:/projects/base/subfolder/file.txt'

# storing the destination path in the
# destination variable
destination = 'D:/projects/base'

# calling the shutil.copy2 method
shutil.copy2(source,destination)
```

运行此代码后，我们会注意到名为 file.txt 的文件已被复制到基本文件夹。

![](img/f08bb658ca2766bf828249e4bb5c7e55.png)

### 方法 4:使用 shutil.copyfileobj()

[shutil.copyfileobj()](https://www.geeksforgeeks.org/python-shutil-copyfileobj-method/) 也类似于上面讨论的方法，但不同的是，首先它采用文件对象而不是文件路径，其次它采用一个额外的选项参数，即复制过程中保留在内存中的字节数。默认值为 16KB。

使用上述方法复制的代码将是:

## 计算机编程语言

```py
# importing shutil module
import shutil

# Source file
source = 'D:/projects/base/subfolder/file.txt'

# Open the source file
# in read mode and
# get the file object
fsrc = open(source, 'r')

# destination file
dest = 'D:/projects/base/file.txt'

# Open the destination file
# in write mode and
# get the file object
fdst = open(dest, 'w')

# Now, copy the contents of
# file object f1 to f2
# using shutil.copyfileobj() method
shutil.copyfileobj(fsrc, fdst)

# We can also specify
# the buffer size by passing
# optional length parameter
# like shutil.copyfileobj(fsrc, fdst, 1024)

# Close file objects
fdst.close()
fsrc.close()
```

运行此代码后，我们会注意到名为 file.txt 的文件已被复制到基本文件夹。

![](img/f08bb658ca2766bf828249e4bb5c7e55.png)

我们还可以使用给定的表格记住上述方法之间的区别:

![](img/39278405bf5fa72158f45f581b5231b0.png)