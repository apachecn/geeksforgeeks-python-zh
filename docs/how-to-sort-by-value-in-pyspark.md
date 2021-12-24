# 在 PySpark 中如何按值排序？

> 原文:[https://www . geesforgeks . org/如何按 pyspark 中的值排序/](https://www.geeksforgeeks.org/how-to-sort-by-value-in-pyspark/)

在本文中，我们将在 PySpark 中按值排序。

创建 RDD 进行演示:

```py
# importing module
from pyspark.sql import SparkSession, Row

# creating sparksession and giving an app name
spark = SparkSession.builder.appName('sparkdf').getOrCreate()

# create 2 Rows with 3 columns
data = Row(First_name="Sravan", Last_name="Kumar", age=23),
Row(First_name="Ojaswi", Last_name="Pinkey", age=16),
Row(First_name="Rohith", Last_name="Devi", age=7)

# create row on rdd
rdd = spark.sparkContext.parallelize(data)

# display data
rdd.collect()
```