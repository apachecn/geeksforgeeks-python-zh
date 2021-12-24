# 如何删除 PySpark 数据框中的列？

> 原文:[https://www . geesforgeks . org/how-delete-columns-in-py spark-data frame/](https://www.geeksforgeeks.org/how-to-delete-columns-in-pyspark-dataframe/)

在本文中，我们将删除 Pyspark 数据框中的列。为此，我们将使用 drop()函数。此函数可用于从数据框中移除值。

> **语法:** dataframe.drop('列名')

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

**示例 1:** Python 程序删除单个列。

这里我们将从数据框中删除“学生标识”，为此我们将使用 drop()。

## 蟒蛇 3

```py
# delete single column
dataframe=dataframe.drop('student ID')
dataframe.show()
```

**输出:**

```py
+------------+-------+
|student NAME|college|
+------------+-------+
|      sravan| vignan|
|      ojaswi|   vvit|
|      rohith|   vvit|
|     sridevi| vignan|
|      sravan| vignan|
|     gnanesh|    iit|
+------------+-------+
```

**例 2:删除多列**

在这里，我们将删除数据框中的多个列，只需在 drop()函数中传递多个列。

## 蟒蛇 3

```py
# delete two columns
dataframe=dataframe.drop(*('student NAME',
                           'student ID'))
dataframe.show()
```

**输出:**

```py
+-------+
|college|
+-------+
| vignan|
|   vvit|
|   vvit|
| vignan|
| vignan|
|    iit|
+-------+
```

**例 3:删除所有列**

这里我们将删除 dataframe 中的所有列。

## 蟒蛇 3

```py
# delete two columns
dataframe=dataframe.drop(*('student NAME',
                           'student ID',
                           'college'))
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