# 从 PySpark 数据框中获取特定行

> 原文:[https://www . geesforgeks . org/get-specific-row-from-py spark-data frame/](https://www.geeksforgeeks.org/get-specific-row-from-pyspark-dataframe/)

在本文中，我们将讨论如何从 PySpark 数据框中获取特定的行。

**创建用于演示的数据框:**

## python 3

```py
# importing module
import pyspark

# importing sparksession
# from pyspark.sql module
from pyspark.sql import SparkSession

# creating sparksession
# and giving an app name
spark = SparkSession.builder.appName('sparkdf').getOrCreate()

# list  of employee data with 5 row values
data = [["1", "sravan", "company 1"],
        ["2", "ojaswi", "company 2"],
        ["3", "bobby", "company 3"],
        ["4", "rohith", "company 2"],
        ["5", "gnanesh", "company 1"]]

# specify column names
columns = ['Employee ID', 'Employee NAME',
           'Company Name']

# creating a dataframe from the lists of data
dataframe = spark.createDataFrame(data, columns)

# display dataframe
dataframe.show()
```