# Python | filecmp.cmpfiles()方法

> 原文:[https://www . geesforgeks . org/python-file CMP-CMP files-method/](https://www.geeksforgeeks.org/python-filecmp-cmpfiles-method/)

**Python 中的 Filecmp 模块**提供了比较文件和目录的功能。该模块属于 Python 的标准实用程序模块。除了文件和目录中的数据之外，本模块还考虑用于比较的文件和目录的属性。

Python 中的`**filecmp.cmpfiles()**`方法用于比较两个目录中的文件。使用此方法可以比较多个文件。该方法返回三个文件名列表，即`match`、`mismatch`和`errors`。`match`列表包含比较匹配的文件列表，`mismatch`列表包含不匹配的文件名称，`errors`列表包含无法比较的文件名称。

默认情况下，该方法执行浅层比较(默认情况下为`shallow = True`)，这意味着只有 [os.stat()](https://www.geeksforgeeks.org/python-os-stat-method/) 签名(如大小、修改日期等)。)的文件进行比较，如果它们具有相同的签名，则不管文件的内容如何，文件都被认为是相等的。如果`shallow`设置为`False`，则通过比较文件的内容进行比较。

> **语法:** filecmp.cmpfiles(dir1，dir2，浅层= True)
> 
> **参数:**
> **dir1** :第一个目录的路径。它可以是字符串、字节或操作系统。表示目录路径的类路径对象。
> **dir2** :第二个目录的路径。它可以是字符串、字节或操作系统。表示目录路径的类路径对象。
> **常用**:表示将在 dir1 和 dir2 中进行比较的文件名称的列表。
> **(可选):布尔值“真”或“假”。此参数的默认值为“真”。如果其值为真，则仅比较文件的元数据。如果为假，则比较文件的内容。**
> 
> ****返回类型:**该方法返回一个三元组列表，代表匹配、不匹配和错误列表。**

**例如:**

> ****filecmp.cmpfiles(dir1，dir2，[file1，file2，fil3])** 将比较 **dir1/file1** 与 **dir2/file1** 、 **dir1/file2** 与 **dir2/file2** 、 **dir1/file3** 与 **dir2/file3** 并将返回匹配、不匹配和错误列表。**

****Example:** Use of filecmp.cmpfiles() method to compare files in two directories.

```py
# Python program to explain filecmp.cmpfiles() method 

# importing filecmp module 
import filecmp

# Path of first directory
dir1 = "/home / User / Documents"

# Path of second directory
dir2 = "/home / User / Desktop"

# Common files
common = ["file1.txt", "file2.txt", "file3.txt"]

# Shallow compare the files
# common in both directories  
match, mismatch, errors = filecmp.cmpfiles(dir1, dir2, common)

# Print the result of
# shallow comparison
print("Shallow comparison:")
print("Match :", match)
print("Mismatch :", mismatch)
print("Errors :", errors, "\n")

# Compare the
# contents of both files
# (i.e deep comparison)
match, mismatch, errors = filecmp.cmpfiles(dir1, dir2, common,
                                              shallow = False)

# Print the result of
# deep comparison
print("Deep comparison:")
print("Match :", match)
print("Mismatch :", mismatch)
print("Errors :", errors)
```

**Output:**

```py
Shallow comparison:
Match : ['file1.txt', 'file2.txt', 'file3.txt']
Mismatch : []
Errors : []  

Deep comparison:
Match : ['file1.txt', 'file2.txt']
Mismatch : ['file3.txt']
Errors : []

```**