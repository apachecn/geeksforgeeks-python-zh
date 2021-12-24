# 在 Python 中处理 OSError 异常

> 原文:[https://www . geesforgeks . org/handling-oserror-exception-in-python/](https://www.geeksforgeeks.org/handling-oserror-exception-in-python/)

让我们看看如何处理 Python 中的错误异常。 **osError** 是 Python 中的内置异常，作为 **os** 模块的错误类，当 OS 特定的系统函数返回系统相关错误时，包括“文件未找到”或“磁盘已满”等 I/O 故障，就会引发该错误类。

下面是一个错误示例:

## 计算机编程语言

```py
# Importing os module
import os

# os.ttyname() method in Python is used to get the terminal 
# device associated with the specified file descriptor.
# and raises an exception if the specified file descriptor 
# is not associated with any terminal device.
print(os.ttyname(1))
```

**输出:**

```py
OSError: [Errno 25] Inappropriate ioctl for device

```

我们可以使用[try…来处理 ODError 异常，除了](https://www.geeksforgeeks.org/python-try-except/)语句。

## 计算机编程语言

```py
# importing os module  
import os 

# create a pipe using os.pipe() method 
# it will return a pair of  
# file descriptors (r, w) usable for 
# reading and writing, respectively. 
r, w = os.pipe() 

# (using exception handling technique) 
# try to get the terminal device associated  
# with the file descriptor r or w 
try : 
    print(os.ttyname(r))  

except OSError as error : 
    print(error) 
    print("File descriptor is not associated with any terminal device") 
```

**Output :**

```py
[Errno 25] Inappropriate ioctl for device
File descriptor is not associated with any terminal device
```