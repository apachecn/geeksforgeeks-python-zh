# Python |创建一个以当前日期为名称的空文本文件

> 原文:[https://www . geesforgeks . org/python-创建一个以当前日期为名称的空文本文件/](https://www.geeksforgeeks.org/python-create-an-empty-text-file-with-current-date-as-its-name/)

在本文中，我们将学习如何创建一个文本文件名作为其中的当前日期。为此，我们可以使用 datetime 模块的 now()方法。

datetime 模块提供了以简单和复杂的方式操作日期和时间的类。虽然支持日期和时间算法，但实现的重点是输出格式化和操作的高效属性提取。

让我们看一个代码示例，并尝试更好地理解它。

```
# Python script to create an empty file
# with current date as name.

# importing datetime module
import datetime

# datetime.datetime.now() to get 
# current date as filename.
filename = datetime.datetime.now()

# create empty file
def create_file():
    # Function creates an empty file
    # %d - date, %B - month, %Y - Year
    with open(filename.strftime("%d %B %Y")+".txt", "w") as file:
        file.write("")

# Driver Code
create_file()
```

**输出:**

```
01 August 2019.txt
```