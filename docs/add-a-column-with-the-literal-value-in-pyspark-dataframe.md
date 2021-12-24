# 在 PySpark 数据框

中添加一列文字值

> 原文:[https://www . geesforgeks . org/add-a-column-with-literal-value-in-py spark-data frame/](https://www.geeksforgeeks.org/add-a-column-with-the-literal-value-in-pyspark-dataframe/)

在本文中，我们将看到如何在 PySpark Dataframe 中添加一个具有文字值的列。

**创建用于演示的数据框:**

## python 3

```py
# import SparkSession from the pyspark
from pyspark.sql import SparkSession

# build and create the
# SparkSession with name "lit_value"
spark = SparkSession.builder.appName("lit_value").getOrCreate()

# create the spark dataframe with columns A,B
data = spark.createDataFrame([('x',5),('Y',3),
                            ('Z',5) ],['A','B'])

# showing the schema and  table
data.printSchema()
data.show()
```