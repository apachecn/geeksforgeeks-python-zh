# 使用 Python 脚本自动备份

> 原文:[https://www . geeksforgeeks . org/automate-backup-with-python-script/](https://www.geeksforgeeks.org/automate-backup-with-python-script/)

在本文中，我们将看到如何使用 Python 脚本自动备份。

文件备份对于将数据保存在本地存储中至关重要。我们将使用 **shutil** 、 **os** 和 **sys** 模块。在这种情况下，shutil 模块用于将数据从一个文件复制到另一个文件，而 os 和 sys 模块用于获取目录路径等等。

## **分步实施:**

**步骤 1:** 导入以下模块

## 蟒蛇 3

```py
import shutil
from datetime import date
import os
import sys
```

**步骤 2:** 现在让我们使用日期时间模块获取今天的日期。

## 蟒 3

```py
today = date.today()
date_format = today.strftime("%d_%b_%Y_")
```

**步骤 3:** 如果用户指定了源文件的路径，使用下面的行将源文件的路径与源文件的名称连接起来。

## 蟒 3

```py
src_dir = src_dir+src_file_name
```

如果不是，并且您的文件存储在与当前 Python 脚本相同的目录中，请使用 os 模块确定文件的当前路径，并通过将 os 模块提供的路径与源文件名相结合来创建源目录。

## 蟒 3

```py
os.chdir(sys.path[0])
```

**第四步:**如果用户没有指定源文件名，我们必须返回一个文件不存在的错误。

## 蟒蛇 3

```py
if not src_file_name:
   print("Please give atleast the Source File Name")
```

**第五步:**现在，用下面的案例来测试必要的条件。

如果用户提供了所有输入，如**源文件名**、**源文件路径**、**目标文件名**、**目标文件路径**。

## 蟒 3

```py
if src_file_name and dst_file_name and src_dir and dst_dir:
     src_dir = src_dir+src_file_name
     dst_dir = dst_dir+dst_file_name
```

如果目标文件名为“无”，表明用户没有指定目标文件名，则使用下面列出的条件。

## 蟒 3

```py
elif dst_file_name is None or not dst_file_name:
       dst_file_name = src_file_name
       dst_dir = dst_dir+date_format+dst_file_name
```

如果用户输入一个包含一个或多个空格的空字符串。

## 蟒 3

```py
elif dst_file_name.isspace():
      dst_file_name = src_file_name
      dst_dir = dst_dir+date_format+dst_file_name
```

如果用户输入备份副本的名称，只需连接**目标目录**、**日期**和**目标文件名**即可创建输出文件名。

## 蟒 3

```py
else:
      dst_dir = dst_dir+date_format+dst_file_name
```