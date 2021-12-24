# 如何在 Python 中获取文件的权限屏蔽

> 原文:[https://www . geesforgeks . org/如何获取 python 中文件的权限屏蔽/](https://www.geeksforgeeks.org/how-to-get-the-permission-mask-of-a-file-in-python/)

**先决条件:** [Python | os.umask()方法](https://www.geeksforgeeks.org/python-os-umask-method/)

在类似 UNIX 的操作系统中，新文件是用一组默认权限创建的。我们可以通过应用权限屏蔽来限制或提供任何特定的或一组权限。使用 Python，我们可以获取或设置文件的权限屏蔽。

在本文中，我们将讨论如何在 Python 中获取文件的权限屏蔽。

> **使用的方法–**
> 
> **[os.stat()](https://www.geeksforgeeks.org/python-os-stat-method/)** :此方法用于在指定路径上执行`stat()`系统调用。此方法用于获取指定路径的状态。

下面是获取文件权限屏蔽的 Python 程序–

```py
# Python program to get file permission mask
# of a given file

# Import os module
import os

# File
filename = "./file.txt"

# Now get the status of the file
# using os.stat() method
print("Status of %s:" %filename)
status = os.stat(filename)

# os.stat() method will return a
# stat_result’ object of ‘os.stat_result’ class
# which will represent 
# the status of file.
print(status)

# st_mode attribute of
# returned 'stat_result' object
# will represent the file type and
# file mode bits (permissions).
print("\nFile type and file permission mask:", status.st_mode)

# st_mode attribute is an integer value
# but we are interested in octal value
# for file's permission mask

# So we will change the integer value
# to octal value
print("File type and file permission mask(in octal):",
                                  oct(status.st_mode))

# last 3 octal digit 
# represents the file permission mask
# and upper parts tells the file type 
# so to get the file's permission 
# we will extract last 3 octal digit
# of status.st_mode
print("\nFile permission mask (in octal):", oct(status.st_mode)[-3:])

# Alternate way
print("File permission mask (in octal):", oct(status.st_mode & 0o777))
```

**Output:**

```py
Status of ./file.txt:
os.stat_result(st_mode=33188, st_ino=801303, st_dev=2056, st_nlink=1,
st_uid=1000, st_gid=1000, st_size=409, st_atime=1561590918, st_mtime=1561590910,
st_ctime=1561590910)

File type and file permission mask: 33188
File type and file permission mask(in octal): 0o100644

File permission mask (in octal): 644
File permission mask (in octal): 0o644

```

以下程序是上述程序的简短版本–

```py
# Python program to get file permission mask
# of a given file

# Import os module
import os

# File
filename = "./file.txt"

# Get the file permission mask
# of the specified file
mask = oct(os.stat(filename).st_mode)[-3:]

# Print the mask
print("File permission mask:", mask)
```

**Output:**

```py
File permission mask: 644

```