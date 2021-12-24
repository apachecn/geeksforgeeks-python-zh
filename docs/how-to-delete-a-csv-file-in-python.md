# 如何删除 Python 中的 CSV 文件？

> 原文:[https://www . geesforgeks . org/how-delete-a-CSV-file-in-python/](https://www.geeksforgeeks.org/how-to-delete-a-csv-file-in-python/)

在本文中，我们将删除 Python 中的一个 CSV 文件。CSV(逗号分隔值文件)是处理表格数据最常用的文件格式。数据值由(逗号)分隔。第一行给出列的名称，下一行给出每列的值。

**进场:**

*   导入模块。
*   检查文件的路径。
*   如果文件存在，我们将使用 os.remove()删除它。

> **语法:** os.remove('路径)

**例 1:删除特定 csv 文件。**

## 蟒蛇 3

```py
# Python program to delete a csv file 
# csv file present in same directory
import os

# first check whether file exists or not
# calling remove method to delete the csv file
# in remove method you need to pass file name and type
file = 'word.csv'
if(os.path.exists(file) and os.path.isfile(file)):
  os.remove(file)
  print("file deleted")
else:
  print("file not found")
```

**输出:**

```py
file deleted
```

**示例 2:删除目录中的所有 csv 文件**

我们可以使用 [os.walk()](https://www.geeksforgeeks.org/os-walk-python/) 功能遍历一个目录，删除特定的文件。在下面的例子中，我们将删除所有的'*。给定目录中的 csv* 文件。

## 蟒蛇 3

```py
import os
for folder, subfolders, files in os.walk('csv/'): 

    for file in files: 

        # checking if file is 
        # of .txt type 
        if file.endswith('.csv'): 
            path = os.path.join(folder, file) 

            # printing the path of the file 
            # to be deleted 
            print('deleted : ', path )

            # deleting the csv file 
            os.remove(path)
```

**输出:**

```py
deleted :  csv/Sample1.csv
deleted :  csv/Sample2.csv
deleted :  csv/Sample3.csv
deleted :  csv/tips.csv
```