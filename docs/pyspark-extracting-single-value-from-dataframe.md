# PySpark–从数据框中提取单个值

> 原文:[https://www . geesforgeks . org/pyspark-extracting-单值 from-dataframe/](https://www.geeksforgeeks.org/pyspark-extracting-single-value-from-dataframe/)

在本文中，我们将从 pyspark dataframe 列中提取一个值。为此，我们将使用 first()和 head()函数。

单个值意味着只有一个值，我们可以根据列名提取这个值

> **语法**:
> 
> *   dataframe.first()['列名']
> *   Dataframe.head()['Index']
> 
> **在哪里，**
> 
> *   dataframe 是输入数据帧，列名是特定的列
> *   索引是行和列。

**所以我们将使用嵌套列表创建数据帧。**

## 蟒蛇 3

```
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

```
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

**示例 1:** 使用 first()从特定列中提取单个值的 Python 程序。

## 蟒蛇 3

```
# extract single value based on
# column in the dataframe
dataframe.first()['student ID']
```

**输出:**

```
'1'
```

**示例 2:** 使用 head()提取单个值。

## 蟒蛇 3

```
# extract single value based
# on column in the dataframe
dataframe.head()[0]
```

**输出:**

```
'1'
```

**示例 3:** 使用 head()提取单个值。

## 蟒蛇 3

```
# extract single value based
# on column in the dataframe
dataframe.head()[2]
```

**输出:**

```
'vignan'
```