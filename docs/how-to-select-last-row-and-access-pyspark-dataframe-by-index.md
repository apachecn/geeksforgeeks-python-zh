# 如何通过索引选择最后一行并访问 PySpark 数据帧？

> 原文:[https://www . geesforgeks . org/如何按索引选择最后一行并访问 py spark-data frame/](https://www.geeksforgeeks.org/how-to-select-last-row-and-access-pyspark-dataframe-by-index/)

在本文中，我们将讨论如何选择最后一行并通过索引访问 pyspark dataframe。

**创建用于演示的数据框:**

## python 3

```
# importing module
import pyspark

# importing sparksession from pyspark.sql module
from pyspark.sql import SparkSession

# creating sparksession and giving an app name
spark = SparkSession.builder.appName('sparkdf').getOrCreate()

# list  of students  data
data = [["1","sravan","vignan"],
       ["2","ojaswi","vvit"],
       ["3","rohith","vvit"],
       ["4","sridevi","vignan"],
       ["1","sravan","vignan"],
       ["5","gnanesh","iit"]]

# specify column names
columns = ['student ID','student NAME','college']

# creating a dataframe from the lists of data
dataframe = spark.createDataFrame(data,columns)

# show dataframe
dataframe.show()
```