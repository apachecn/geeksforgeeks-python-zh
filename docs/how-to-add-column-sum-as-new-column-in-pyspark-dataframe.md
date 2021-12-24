# 如何在 PySpark 数据框中添加列和作为新列？

> 原文:[https://www . geesforgeks . org/how-add-column-sum-as-new-column-in-pyspark-data frame/](https://www.geeksforgeeks.org/how-to-add-column-sum-as-new-column-in-pyspark-dataframe/)

在本文中，我们将看到如何通过各种方法在 Pyspark 数据框中添加新列。这意味着我们想要创建一个新的列，它将包含给定行中所有值的总和。现在让我们讨论各种方法如何将 sum 作为新列添加

但首先，让我们为演示创建数据框

## python 3

```py
# import SparkSession from the pyspark
from pyspark.sql import SparkSession

# build and create  the SparkSession
# with name "sum as new_col"
spark = SparkSession.builder.appName("sum as new_col").getOrCreate()

# Creating the Spark DataFrame
data = spark.createDataFrame([('x', 5, 3, 7),
                              ('Y', 3, 3, 6),
                              ('Z', 5, 2, 6)],
                             ['A', 'B', 'C', 'D'])

# Print the schema of the DataFrame by
# printSchema()
data.printSchema()

# Showing the DataFrame
data.show()
```