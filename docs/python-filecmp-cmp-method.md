# Python: filecmp.cmp()方法

> 原文:[https://www.geeksforgeeks.org/python-filecmp-cmp-method/](https://www.geeksforgeeks.org/python-filecmp-cmp-method/)

**Python 中的 Filecmp 模块**提供了比较文件和目录的功能。该模块属于 Python 的标准实用程序模块。除了文件和目录中的数据之外，本模块还考虑用于比较的文件和目录的属性。

Python 中的`filecmp.cmp()`方法用于比较两个文件。默认情况下，该方法执行浅比较(默认情况下为`shallow = True`)，这意味着只有 [`os.stat()`](https://www.geeksforgeeks.org/python-os-stat-method/) 签名(如大小、修改日期等)。)进行比较，如果它们具有相同的签名，则无论文件的内容如何，文件都被认为是相等的。如果`shallow`设置为`False`，则通过比较两个文件的内容进行比较。

> **语法:** filecmp.cmp(file1，file2，浅层=真)
> 
> **参数:**
> **文件 1** :要比较的第一个文件的路径。它可以是字符串、字节、os。PathLike 对象或表示文件路径的整数。
> **文件 2** :要比较的第二个文件的路径。它可以是字符串、字节、os。PathLike 对象或表示文件路径的整数。
> **浅(可选):**布尔值“真”或“假”。此参数的默认值为“真”。如果其值为真，则仅比较文件的元数据。如果为假，则比较文件的内容。
> 
> **返回类型:**如果指定的文件相等，该方法返回布尔值“真”，否则返回“假”。

**Code:** Use of filecmp.cmp() method to compare two files

```py
# Python program to demonstrate
# filecmp.cmp() method 

import filecmp

# Path of first file
file1 = "/home/geeks/Desktop/gfg/data.txt"

# Path of second file
file2 = "/home/geeks/Desktop/gfg/gfg.txt"

# Compare the os.stat()
# signature i.e the metadata
# of both files 
comp = filecmp.cmp(file1, file2)

# Print the result of comparison
print(comp)

# Compare the
# contents of both files
comp = filecmp.cmp(file1, file2, shallow = False)

# Print the result of comparison
print(comp)
```

**Output:**

```py
False
True

```