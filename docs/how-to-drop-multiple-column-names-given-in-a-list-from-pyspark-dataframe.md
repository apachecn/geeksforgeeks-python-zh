# 如何从 PySpark DataFrame 中删除列表中给出的多个列名？

> 原文:[https://www . geeksforgeeks . org/如何删除多列名称-从 pyspark 列表中给出-dataframe/](https://www.geeksforgeeks.org/how-to-drop-multiple-column-names-given-in-a-list-from-pyspark-dataframe/)

在本文中，我们将删除 Python 中 Pyspark 数据框中列表中给出的多个列。

为此，我们将使用 **drop()** 功能。此函数用于从数据框中移除值。

> **语法:** dataframe.drop(*['列 1 '，'列 2 '，'列 n'])
> 
> 哪里，
> 
> *   数据帧是输入数据帧
> *   列名是通过 dataframe 中的列表传递的列。

**创建三列学生数据框的 Python 代码:**

## 蟒蛇 3

```py
# importing module
import pyspark

# importing sparksession from pyspark.sql module
from pyspark.sql import SparkSession

# creating sparksession and giving an app name
spark = SparkSession.builder.appName('sparkdf').getOrCreate()

# list  of students  data 
data =[["1","sravan","vignan"],
       ["2","ojaswi","vvit"],
       ["3","rohith","vvit"],
       ["4","sridevi","vignan"],
       ["1","sravan","vignan"], 
       ["5","gnanesh","iit"]]

# specify column names
columns=['student ID','student NAME','college']

# creating a dataframe from the lists of data
dataframe = spark.createDataFrame(data,columns)

print("Actual data in dataframe")

# show dataframe
dataframe.show()
```

**输出:**

```py
Actual data in dataframe
+----------+------------+-------+
|student ID|student NAME|college|
+----------+------------+-------+
|         1|      sravan| vignan|
|         2|      ojaswi|   vvit|
|         3|      rohith|   vvit|
|         4|     sridevi| vignan|
|         1|      sravan| vignan|
|         5|     gnanesh|    iit|
+----------+------------+-------+
```

**示例 1:** 程序删除多个列名称作为列表。

## 蟒蛇 3

```py
list = ['student NAME','college']

# drop two  columns in dataframe
dataframe = dataframe.drop(*list)
dataframe.show()
```

**输出:**

```py
+----------+
|student ID|
+----------+
|         1|
|         2|
|         3|
|         4|
|         1|
|         5|
+----------+
```

**示例 2:** 示例程序将一列名称作为列表删除。

## 蟒蛇 3

```py
list = ['college']

# drop two  columns in dataframe
dataframe=dataframe.drop(*list)
dataframe.show()
```

**输出:**

```py
+----------+------------+
|student ID|student NAME|
+----------+------------+
|         1|      sravan|
|         2|      ojaswi|
|         3|      rohith|
|         4|     sridevi|
|         1|      sravan|
|         5|     gnanesh|
+----------+------------+
```

**示例 3:** 将所有列名作为列表删除。

## 蟒蛇 3

```py
list = ['student ID','student NAME','college']

# drop all  columns in dataframe
dataframe=dataframe.drop(*list)
dataframe.show()
```

**输出:**

```py
++
||
++
||
||
||
||
||
||
++
```