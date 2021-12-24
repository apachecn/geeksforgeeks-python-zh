# 使用 Python 删除目录或文件

> 原文:[https://www . geesforgeks . org/delete-a-directory-or-file-use-python/](https://www.geeksforgeeks.org/delete-a-directory-or-file-using-python/)

Python 为移除文件和目录提供了不同的方法和功能。人们可以根据自己的需要取出文件。Python 提供的各种方法有–

*   [使用 os.remove()](#remove)
*   [使用 os.rmdir()](#rmdir)
*   [使用 shutil.rmtree()](#rmtree)

## 使用 os.remove()

**[Python 中的 OS 模块](https://www.geeksforgeeks.org/os-module-python-examples/)** 提供了与操作系统交互的功能。os 模块中的所有函数在文件名和路径无效或不可访问的情况下都会引发`**OSError**` ，或者其他具有正确类型但不被操作系统接受的参数。

Python 中的`os.remove()`方法用于移除或删除文件路径。此方法**不能删除目录**。如果指定的路径是目录，则方法将引发`OSError` 。

> **语法:** os.remove(路径，* dir _ FD =无)
> 
> **参数:**
> **路径:**表示文件路径的类路径对象。类似路径的对象是表示路径的字符串或字节对象。
> **dir_fd(可选):**引用目录的文件描述符。此参数的默认值为“无”。
> 如果指定的路径是绝对的，那么 dir_fd 被忽略。
> 
> **注意:**参数列表中的“*”表示以下所有参数(在我们的例子中为‘dir _ FD’)都是仅包含关键字的参数，并且可以使用它们的名称来提供，而不是作为位置参数。
> 
> **返回类型:**此方法不返回值。

**示例 1:** 假设文件夹中包含的文件为:
![python-os.remove](img/ab3dc3d44c640b0606a6393b77842fc7.png)

我们想从上面的文件夹中删除文件 1。下面是实现。

```
# Python program to explain os.remove() method  

# importing os module  
import os 

# File name 
file = 'file1.txt'

# File location 
location = "D:/Pycharm projects/GeeksforGeeks/Authors/Nikhil/"

# Path 
path = os.path.join(location, file) 

# Remove the file 
# 'file.txt' 
os.remove(path) 
```

**输出:**
![python-os.remove](img/9c4ff3f3b8586776d2a17f966d54cf75.png)

**例 2:** 如果指定的路径是目录。

```
# Python program to explain os.remove() method  

# importing os module  
import os 

# Directory name
dir = "Nikhil"

# Path 
location = "D:/Pycharm projects/GeeksforGeeks/Authors/"
path = os.path.join(location, dir)

# Remove the specified 
# file path 
os.remove(path) 
print("% s has been removed successfully" % dir) 

# if the specified path  
# is a directory then  
# 'IsADirectoryError' error 
# will raised  

# Similarly if the specified 
# file path does not exists or   
# is invalid then corresponding 
# OSError will be raised 
```

**输出:**

```
Traceback (most recent call last):
  File "osremove.py", line 11, in 
    os.remove(path)
IsADirectoryError: [Errno 21] Is a directory: 'D:/Pycharm projects/GeeksforGeeks/Authors/Nikhil'

```

**例 3:** 使用`os.remove()`方法处理错误。

```
# Python program to explain os.remove() method  

# importing os module  
import os 

# path 
path = 'D:/Pycharm projects/GeeksforGeeks/Authors/Nikhil'

# Remove the specified  
# file path 
try: 
    os.remove(path) 
    print("% s removed successfully" % path) 
except OSError as error: 
    print(error) 
    print("File path can not be removed") 
```

**输出:**

```
[Errno 21] Is a directory: 'D:/Pycharm projects/GeeksforGeeks/Authors/Nikhil'
File path can not be removed

```

**注:**想了解更多`os.remove()` [点击此处](https://www.geeksforgeeks.org/python-os-remove-method/)。

## 使用 os.rmdir()

Python 中的`os.rmdir()`方法用于移除或删除空目录。 **`OSError`** 如果指定的路径不是空目录就会被引发。

> **语法:** os.rmdir(路径，* dir _ FD =无)
> 
> **参数:**
> **路径:**表示文件路径的类路径对象。类似路径的对象是表示路径的字符串或字节对象。
> **dir_fd(可选):**引用目录的文件描述符。此参数的默认值为“无”。
> 如果指定的路径是绝对的，那么 dir_fd 被忽略。
> 
> **注意:**参数列表中的“*”表示以下所有参数(在我们的例子中为‘dir _ FD’)都是仅包含关键字的参数，并且可以使用它们的名称来提供，而不是作为位置参数。
> 
> **返回类型:**此方法不返回值。

**示例 1:** 假设目录是–

![python-os.rmdir](img/9e3f80669aac577a19d56a60e71e2186.png)

我们想删除目录极客。下面是实现。

```
# Python program to explain os.rmdir() method  

# importing os module  
import os 

# Directory name 
directory = "Geeks"

# Parent Directory 
parent = "D:/Pycharm projects/"

# Path 
path = os.path.join(parent, directory) 

# Remove the Directory 
# "Geeks" 
os.rmdir(path) 
```

**输出:**

![python-os.rmdir](img/b3bb910d2585c1650cef4b7b6b163eb7.png)

**例 2:** 处理错误而`using os.rmdir()`方法，

```
# Python program to explain os.rmdir() method

# importing os module  
import os

# Directory name 
directory = "GeeksforGeeks"

# Parent Directory 
parent = "D:/Pycharm projects/"

# Path 
path = os.path.join(parent, directory)

# Remove the Directory
# "GeeksforGeeks"
try:
    os.rmdir(path)
    print("Directory '% s' has been removed successfully" % directory)
except OSError as error:
    print(error)
    print("Directory '% s' can not be removed" % directory)

# if the specified path
# is not an empty directory 
# then permission error will 
# be raised 

# similarly if specified path 
# is invalid or is not a  
# directory then corresponding 
# OSError will be raised 
```

**输出:**

```
[WinError 145] The directory is not empty: 'D:/Pycharm projects/GeeksforGeeks'
Directory 'GeeksforGeeks' can not be removed

```

**注:**想了解更多`os.rmdir()` [点击此处](https://www.geeksforgeeks.org/python-os-rmdir-method/)。

## 使用 shutil.rmtree()

shutil.rmtree()用于删除整个目录树，路径必须指向一个目录(但不是指向一个目录的符号链接)。

> **语法:** shutil.rmtree(路径，ignore_errors=False，onerror=None)
> 
> **参数:**
> **路径:**表示文件路径的类路径对象。类似路径的对象是表示路径的字符串或字节对象。
> **ignore_errors:** 如果 ignore_errors 为真，则删除失败导致的错误将被忽略。
> **oneerror:** 如果 ignore_errors 为 false 或省略，则通过调用 oneerror 指定的处理程序来处理此类错误。

**例 1:** 假设目录和子目录如下。

**#父目录:**
![python-shutil.rmtree](img/3136a3b16bc368d766d2f1ad52f9e2c0.png)

**#父目录内目录:**
![python-shutil.rmtree](img/6a8ee7c2e99ed708e5685a8be970c7eb.png)

**#文件内子目录:**
![python-shutil.rmtree](img/f43a4dddb9fa147575b0cbfbace9aa04.png)

我们想删除目录作者。下面是实现。

```
# Python program to demonstrate
# shutil.rmtree()

import shutil
import os

# location
location = "D:/Pycharm projects/GeeksforGeeks/"

# directory
dir = "Authors"

# path
path = os.path.join(location, dir)

# removing directory
shutil.rmtree(path)
```

**输出:**

![python-shutil.rmtree](img/3266bfd4fa4db10ee09fd759eccf0f12.png)

**例 2:** 路过`ignore_errors = True`。

```
# Python program to demonstrate
# shutil.rmtree()

import shutil
import os

# location
location = "D:/Pycharm projects/GeeksforGeeks/"

# directory
dir = "Authors"

# path
path = os.path.join(location, dir)

# removing directory
shutil.rmtree(path, ignore_errors = False)

# making ignore_errors = True will not raise 
# a FileNotFoundError
```

**输出:**

> 回溯(最近一次调用最后一次):
> 文件“D:/Pycharm project/gfg/gfg . py”，第 16 行，在 <module>shutil.rmtree(路径，ignore_errors=False)
> 文件“C:\ Users \ Nikhil Aggarwal \ AppData \ Local \ Programs \ Python \ Python 38-32 \ lib \ shutil . py”，第 730 行，在 rmtree
> return _rmtree_unsafe(路径，onerror)
> 文件“C:\ Users \ shutil</module>

**示例 3:** 通过在`onerror` 中传递一个错误
，应该传递一个必须包含三个参数的函数。

*   **函数–**引发异常的函数。
*   **路径–**传递的路径名在移除时引发了异常
*   **exit info–**sys . exc _ info()引发的异常信息

下面是实现

```
# Python program to demonstrate
# shutil.rmtree()

import shutil
import os

# exception handler
def handler(func, path, exc_info):
    print("Inside handler")
    print(exc_info)

# location
location = "D:/Pycharm projects/GeeksforGeeks/"

# directory
dir = "Authors"

# path
path = os.path.join(location, dir)

# removing directory
shutil.rmtree(path, onerror = handler)
```

**输出:**

> 内部处理程序
> ( <class>、文件未找到错误(2、【系统找不到指定路径】 )、 <traceback object="" at="">)
> 内部处理程序
> ( <class>、文件未找到错误(2、【系统找不到指定文件】 )、 <traceback object="" at="">)</traceback></class></traceback></class>