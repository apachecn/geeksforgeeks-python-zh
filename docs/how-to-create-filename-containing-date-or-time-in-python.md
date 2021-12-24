# 如何在 Python 中创建包含日期或时间的文件名

> 原文:[https://www . geesforgeks . org/如何创建包含文件名的日期或时间 python/](https://www.geeksforgeeks.org/how-to-create-filename-containing-date-or-time-in-python/)

**先决条件:** [日期时间模块](https://www.geeksforgeeks.org/python-datetime-module/)

在本文中，我们将看到如何使用 Python 创建带有日期或时间的文件名。

为此，我们将使用 DateTime 模块。首先导入模块，然后用 [datetime.now()](https://www.geeksforgeeks.org/python-now-function/) 对象获取当前时间。现在将其转换为字符串，然后使用 file 对象创建一个文件，就像使用 python 中的文件处理概念创建常规文件一样。

**示例 1:** 创建包含日期/时间的文本文件

## 蟒蛇 3

```
# import module
from datetime import datetime

# get current date and time
current_datetime = datetime.now()
print("Current date & time : ", current_datetime)

# convert datetime obj to string
str_current_datetime = str(current_datetime)

# create a file object along with extension
file_name = str_current_datetime+".txt"
file = open(file_name, 'w')

print("File created : ", file.name)
file.close()
```

**输出:**

> 当前日期和时间:2021-08-19 13:17:48.408908
> 
> 文件创建时间:2021-08-19 13:17:48.408908.txt

如果正确提供了所需的扩展名，可以用这种方式创建任何类型的文件。

**示例 2:** 创建包含日期/时间的 CSV 文件

## 蟒蛇 3

```
# import module
from datetime import datetime

# get current date and time
current_datetime = datetime.now()
print("Current date & time : ", current_datetime)

# convert datetime obj to string
str_current_datetime = str(current_datetime)

# create a file object along with extension
file_name = str_current_datetime+".csv"
file = open(file_name, 'w')

print("File created : ", file.name)
file.close()
```

**输出:**

> 当前日期和时间:2021-08-19 13:19:29.667423
> 
> 文件创建时间:2021-08-19 13:19:29.667423.csv