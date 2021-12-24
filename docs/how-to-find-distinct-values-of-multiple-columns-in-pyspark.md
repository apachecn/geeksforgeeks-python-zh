# 如何在 PySpark 中找到多列的相异值？

> 原文:[https://www . geeksforgeeks . org/如何在 pyspark/](https://www.geeksforgeeks.org/how-to-find-distinct-values-of-multiple-columns-in-pyspark/) 中找到多列的不同值

在本文中，我们将讨论如何在 PySpark 数据框中找到多个列的不同值。

让我们创建一个示例数据框进行演示:

## python 3

```py
# importing module
import pyspark

# importing sparksession from pyspark.sql module
from pyspark.sql import SparkSession

# creating sparksession and giving an app name
spark = SparkSession.builder.appName('sparkdf').getOrCreate()

# list  of employee data
data = [["1", "Tezas", "Google"],
        ["2", "Mohit Rawat", "Rakuten"],
        ["3", "rohith", "Geeksforgeeks"],
        ["4", "Nancy", "IBM"],
        ["1", "Raghav", "Wipro"],
        ["4", "Komal", "Amazon"]]

# specify column names
columns = ['ID', 'NAME', 'Company']

# creating a dataframe from the lists of data
dataframe = spark.createDataFrame(data, columns)

dataframe.show()
```