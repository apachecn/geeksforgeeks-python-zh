# 如何按多列排序 PysPark 数据框？

> 原文:[https://www . geesforgeks . org/how-to-order-py spark-data frame by multi-columns/](https://www.geeksforgeeks.org/how-to-order-pyspark-dataframe-by-multiple-columns/)

在本文中，我们将使用 pyspark dataframe 中的 orderBy()函数对多个列进行排序。对行进行排序意味着按升序或降序排列行，因此我们将使用嵌套列表创建数据框并获取不同的数据。

**orderBy()** 对一列或多列进行排序的函数。默认情况下，它按升序排序。

> ***语法:** orderBy(*cols，升序=True)*
> 
> ***参数:***
> 
> *   ***列:**需要进行排序的列。*
> *   ***升序:**布尔值表示排序按升序进行*

**以学生数据为信息创建数据框的示例程序:**

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

**示例 1:** Python 程序，通过使用 orderby()函数按降序基于两列对数据帧进行排序来显示数据帧

## 蟒蛇 3

```
# show dataframe by sorting the dataframe based
# on two columns in descending order using orderby() function
dataframe.orderBy(['student ID','student NAME'],
                  ascending=False).show()
```

**输出:**

```
+----------+------------+-------+
|student ID|student NAME|college|
+----------+------------+-------+
|         5|     gnanesh|    iit|
|         4|     sridevi| vignan|
|         3|      rohith|   vvit|
|         2|      ojaswi|   vvit|
|         1|      sravan| vignan|
|         1|      sravan| vignan|
+----------+------------+-------+
```

**示例 2:** Python 程序，通过使用 orderby()函数基于两列按升序对数据帧进行排序来显示数据帧

## 蟒蛇 3

```
# show dataframe by sorting the dataframe
# based on two columns in ascending order
# using orderby() function
dataframe.orderBy(['student ID','student NAME'],
                  ascending=True).show()
```

**输出:**

```
+----------+------------+-------+
|student ID|student NAME|college|
+----------+------------+-------+
|         1|      sravan| vignan|
|         1|      sravan| vignan|
|         2|      ojaswi|   vvit|
|         3|      rohith|   vvit|
|         4|     sridevi| vignan|
|         5|     gnanesh|    iit|
+----------+------------+-------+
```