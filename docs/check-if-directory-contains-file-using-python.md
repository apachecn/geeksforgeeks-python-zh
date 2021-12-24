# 使用 python 检查目录是否包含文件

> 原文:[https://www . geesforgeks . org/check-if-directory-contains-file-use-python/](https://www.geeksforgeeks.org/check-if-directory-contains-file-using-python/)

在 Python 中查找目录是否为空可以使用 **os** 库的`[listdir()](https://www.geeksforgeeks.org/python-os-listdir-method/)`方法来实现。Python 中的操作系统模块提供了与操作系统交互的功能。该模块提供了一种使用操作系统相关功能的可移植方式。

> **语法:** os.listdir( <目录路径>)
> 
> **返回:**目录中存在的文件列表，如果目录为空，则为空列表

现在通过调用`listdir()`方法，我们可以得到目录中存在的所有文件的列表。为了检查目录的空性，我们应该检查返回列表的空性。我们有很多方法可以做到这一点，让我们一个一个地检查它们。

1.  **By comparing the returned list with a hardcoded empty list**
    An empty list can be written as **`[]`**. So we can compare the returned list’s equalness with **`[]`**.

    ```
    # Python program to check
    # if a directory contains file

    import os

    # path of the directory
    directoryPath = "D:/Pycharm projects/GeeksforGeeks/Nikhil"

    # Comparing the returned list to empty list
    if os.listdir(directoryPath) == []:
            print("No files found in the directory.")
        else:
            print("Some files found in the directory.")
    ```

    **输出:**

    ```
    Some files found in the directory.

    ```

2.  **By comparing length of the returned list with 0**
    We can get length of a list by using `len()` method of Python. If the length of the returned list is equal to zero then the directory is empty otherwise not.

    ```
    # Python program to check if
    # a directory contains file

    import os

    # path of the directory
    directoryPath = "D:/Pycharm projects/GeeksforGeeks/Nikhil"

    # Checking the length of list
    if len(os.listdir(directoryPath)) == 0:
            print("No files found in the directory.")
        else:
            print("Some files found in the directory.")
    ```

    **输出:**

    ```
    Some files found in the directory.

    ```

3.  **By comparing the boolean value of the list**
    In the above method, we used explicit comparison of the length of the list. Now we are heading with a more Pythonic way using truth value testing. An empty list is evaluated as False in Python.

    ```
    # Python program to check if
    # a directory is empty

    import os

    # path of the directory
    directoryPath = "D:/Pycharm projects/GeeksforGeeks/Nikhil"

    # Checking the boolean value of list
    if not os.listdir(directoryPath):
            print("No files found in the directory.")
        else:
            print("Some files found in the directory.")
    ```

    **输出:**

    ```
    Some files found in the directory.

    ```

#### 完整的源代码:

```
# Python program to check if
# the directory is empty

import os

# Function for checking if the directory
# containes file or not
def isEmpty(directoryPath):

    # Checking if the directory exists or not
    if os.path.exists(directoryPath):

        # Checking if the directory is empty or not
        if len(os.listdir(directoryPath)) == 0:
            return "No files found in the directory."
        else:
            return "Some files found in the directory."
    else:
        return  "Directory does not exist !"

# Driver's code

# Valid directory
directoryPath = "D:/Pycharm projects/GeeksforGeeks/Nikhil"
print("Valid path:", isEmpty(directoryPath))

# Invalid directory
directoryPath = "D:/Pycharm projects/GeeksforGeeks/Nikhil/GeeksforGeeks"
print("Invalid path:", isEmpty(directoryPath))
```

**输出:**

```
Valid path: Some files found in the directory.
Invalid path: Directory does not exist !

```