# 按 PySpark 数据框中的条件计数值

> 原文:[https://www . geesforgeks . org/count-values-by-condition-in-py spark-data frame/](https://www.geeksforgeeks.org/count-values-by-condition-in-pyspark-dataframe/)

在本文中，我们将按条件计算 Pyspark 数据框列的值。

**创建用于演示的数据框:**

## python 3

```
# importing module
import pyspark

# importing sparksession from
# pyspark.sql module
from pyspark.sql import SparkSession

# creating sparksession and giving an app name
spark = SparkSession.builder.appName('sparkdf').getOrCreate()

# list  of employee data with 10 row values
data = [["1", "sravan", "IT", 45000],
        ["2", "ojaswi", "IT", 30000],
        ["3", "bobby", "business", 45000],
        ["4", "rohith", "IT", 45000],
        ["5", "gnanesh", "business", 120000],
        ["6", "siva nagulu", "sales", 23000],
        ["7", "bhanu", "sales", 34000],
        ["8", "sireesha", "business", 456798],
        ["9", "ravi", "IT", 230000],
        ["10", "devi", "business", 100000],
        ]

# specify column names
columns = ['ID', 'NAME', 'sector', 'salary']

# creating a dataframe from the lists of data
dataframe = spark.createDataFrame(data, columns)

# display dataframe
dataframe.show()
```