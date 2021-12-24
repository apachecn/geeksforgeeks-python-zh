# 用 Python 创建目录

> 原文:[https://www.geeksforgeeks.org/create-a-directory-in-python/](https://www.geeksforgeeks.org/create-a-directory-in-python/)

Python 中的操作系统模块提供了与操作系统交互的功能。操作系统属于 Python 的标准实用程序模块。该模块提供了一种使用操作系统相关功能的可移植方式。`os`和`os.path`模块包括许多与文件系统交互的功能。在文件名和路径无效或不可访问的情况下，或者在其他具有正确类型但不被操作系统接受的参数的情况下，操作系统模块中的所有函数都会产生`OSError` 。

操作系统模块中有不同的方法可用于创建控制器。这些是–

*   [os.mkdir()](#mkdir)
*   [OS . makeders()](#makedirs)

#### 使用 os.mkdir()

Python 中的`os.mkdir()`方法是用指定的数值模式创建一个名为 path 的目录。如果要创建的目录已经存在，该方法将引发`FileExistsError` 。

> **语法:** os.mkdir(路径，模式= 0o777，* dir _ FD =无)
> 
> **参数:**
> **路径:**表示文件系统路径的类路径对象。类似路径的对象是表示路径的字符串或字节对象。
> **模式(可选):**表示待创建目录模式的整数值。如果省略该参数，则使用默认值 Oo777。
> **dir_fd(可选):**引用目录的文件描述符。此参数的默认值为“无”。
> 如果指定的路径是绝对的，那么 dir_fd 被忽略。
> 
> **注意:**参数列表中的“*”表示以下所有参数(在我们的例子中为‘dir _ FD’)都是仅包含关键字的参数，并且可以使用它们的名称来提供，而不是作为位置参数。
> 
> **返回类型:**此方法不返回值。

**示例#1:** 使用`os.mkdir()`方法创建目录/文件

```
# Python program to explain os.mkdir() method

# importing os module
import os

# Directory
directory = "GeeksforGeeks"

# Parent Directory path
parent_dir = "D:/Pycharm projects/"

# Path
path = os.path.join(parent_dir, directory)

# Create the directory
# 'GeeksForGeeks' in
# '/home / User / Documents'
os.mkdir(path)
print("Directory '% s' created" % directory)

# Directory
directory = "Geeks"

# Parent Directory path
parent_dir = "D:/Pycharm projects"

# mode
mode = 0o666

# Path
path = os.path.join(parent_dir, directory)

# Create the directory
# 'GeeksForGeeks' in
# '/home / User / Documents'
# with mode 0o666
os.mkdir(path, mode)
print("Directory '% s' created" % directory)
```

**输出:**

```
Directory 'GeeksforGeeks' created
Directory 'Geeks' created

```

**例 2:** 使用`os.mkdir()`方法时出现错误。

```
# Python program to explain os.mkdir() method  

# importing os module  
import os 

# Directory 
directory = "GeeksForGeeks"

# Parent Directory path 
parent_dir = "D:/Pycharm projects/"

# Path 
path = os.path.join(parent_dir, directory) 

# Create the directory 
# 'GeeksForGeeks' in 
# '/home / User / Documents' 
os.mkdir(path) 
print("Directory '% s' created" % directory) 

# if directory / file that  
# is to be created already 
# exists then 'FileExistsError' 
# will be raised by os.mkdir() method 

# Similarly, if the specified path 
# is invalid 'FileNotFoundError' Error 
# will be raised 
```

**输出:**

```
Traceback (most recent call last):
  File "gfg.py", line 18, in os.mkdir(path)
FileExistsError: [WinError 183] Cannot create a file when that file /
                 /already exists: 'D:/Pycharm projects/GeeksForGeeks' 
```

**示例#3:** 使用`os.mkdir()`方法时处理错误。

```
# Python program to explain os.mkdir() method  

# importing os module  
import os 

# path 
path = 'D:/Pycharm projects / GeeksForGeeks'

# Create the directory 
# 'GeeksForGeeks' in 
# '/home / User / Documents' 
try: 
    os.mkdir(path) 
except OSError as error: 
    print(error)  
```

**输出:**

```
[WinError 183] Cannot create a file when that file/
              /already exists: 'D:/Pycharm projects/GeeksForGeeks'

```

#### 使用 os.makedirs()

Python 中的`os.makedirs()`方法用于递归创建目录。也就是说，在创建叶目录时，如果缺少任何中间级目录，`os.makedirs()`方法将创建它们。
例如，考虑以下路径:

```
D:/Pycharm projects/GeeksForGeeks/Authors/Nikhil

```

假设我们想要创建目录“Nikhil”，但是目录“GeeksForGeeks”和“Authors”在路径中不可用。然后`os.makedirs()`方法会在指定路径中创建所有不可用/缺失的目录。首先创建“极客”和“作者”，然后创建“尼基尔”目录。

> **语法:** os.makedirs(路径，模式= 0o777，exist_ok = False)
> 
> **参数:**
> **路径:**表示文件系统路径的类路径对象。类似路径的对象是表示路径的字符串或字节对象。
> **模式(可选):**表示新创建目录模式的整数值。如果省略该参数，则使用默认值 Oo777。
> **exist_ok(可选):**该参数使用默认值 False。如果目标目录已经存在，如果其值为 False，则引发一个错误，否则不引发。
> 
> **返回类型:**此方法不返回值。

**示例#1:** 使用`os.makedirs()`方法创建目录。

```
# Python program to explain os.makedirs() method  

# importing os module  
import os 

# Leaf directory 
directory = "Nikhil"

# Parent Directories 
parent_dir = "D:/Pycharm projects/GeeksForGeeks/Authors"

# Path 
path = os.path.join(parent_dir, directory) 

# Create the directory 
# 'Nikhil' 
os.makedirs(path) 
print("Directory '% s' created" % directory) 

# Directory 'GeeksForGeeks' and 'Authors' will 
# be created too  
# if it does not exists 

# Leaf directory 
directory = "c"

# Parent Directories 
parent_dir = "D:/Pycharm projects/GeeksforGeeks/a/b"

# mode 
mode = 0o666

path = os.path.join(parent_dir, directory) 

# Create the directory 'c' 

os.makedirs(path, mode) 
print("Directory '% s' created" % directory) 

# 'GeeksForGeeks', 'a', and 'b' 
# will also be created if 
# it does not exists 

# If any of the intermediate level 
# directory is missing  
# os.makedirs() method will 
# create them 

# os.makedirs() method can be  
# used to create a directory tree  
```

**输出:**

```
Directory 'Nikhil' created
Directory 'c' created

```

**例 2:**

```
# Python program to explain os.makedirs() method  

# importing os module  
import os 

# os.makedirs() method will raise 
# an OSError if the directory 
# to be created already exists 

# Directory 
directory = "Nikhil"

# Parent Directory path 
parent_dir = "D:/Pycharm projects/GeeksForGeeks/Authors"

# Path 
path = os.path.join(parent_dir, directory) 

# Create the directory 
# 'Nikhil' 
os.makedirs(path) 
print("Directory '% s' created" % directory) 
```

**输出:**

```
Traceback (most recent call last):
  File "gfg.py", line 22, in os.makedirs(path)
  File "C:\Users\Nikhil Aggarwal\AppData\Local\Programs\Python/
       / \Python38-32\lib\os.py", line 221, in makedirs
    mkdir(name, mode)
FileExistsError: [WinError 183] Cannot create a file when that/
               / file already exists: 'D:/Pycharm projects/GeeksForGeeks/Authors\\Nikhil' 
```

**示例#3:** 使用 os.makedirs()方法处理错误。

```
# Python program to explain os.makedirs() method

# importing os module
import os

# os.makedirs() method will raise
# an OSError if the directory
# to be created already exists
# But It can be suppressed by
# setting the value of a parameter
# exist_ok as True

# Directory
directory = "Nikhil"

# Parent Directory path
parent_dir = "D:/Pycharm projects/GeeksForGeeks/Authors"

# Path
path = os.path.join(parent_dir, directory)

# Create the directory
# 'Nikhil'
try:
    os.makedirs(path, exist_ok = True)
    print("Directory '%s' created successfully" % directory)
except OSError as error:
    print("Directory '%s' can not be created" % directory)

# By setting exist_ok as True
# error caused due already
# existing directory can be suppressed
# but other OSError may be raised
# due to other error like
# invalid path name
```

**输出:**

```
Directory 'Nikhil' created successfully

```