# Pyspark–基于多种条件过滤数据帧

> 原文:[https://www . geesforgeks . org/py spark-filter-data frame-基于多条件/](https://www.geeksforgeeks.org/pyspark-filter-dataframe-based-on-multiple-conditions/)

在本文中，我们将看到如何基于多个条件过滤数据帧。

让我们创建一个数据框进行演示:

## python 3

```
# importing module
import pyspark

# importing sparksession from pyspark.sql module
from pyspark.sql import SparkSession

# creating sparksession and giving an app name
spark = SparkSession.builder.appName('sparkdf').getOrCreate()

# list  of students  data
data = [["1", "Amit", "DU"],
        ["2", "Mohit", "DU"],
        ["3", "rohith", "BHU"],
        ["4", "sridevi", "LPU"],
        ["1", "sravan", "KLMP"],
        ["5", "gnanesh", "IIT"]]

# specify column names
columns = ['student_ID', 'student_NAME', 'college']

# creating a dataframe from the lists of data
dataframe = spark.createDataFrame(data, columns)

# show dataframe
dataframe.show()
```