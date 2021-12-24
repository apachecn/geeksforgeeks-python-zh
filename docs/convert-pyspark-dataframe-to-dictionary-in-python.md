# 将 PySpark 数据帧转换为 Python 中的字典

> 原文:[https://www . geesforgeks . org/convert-py spark-data frame-to-dictionary-in-python/](https://www.geeksforgeeks.org/convert-pyspark-dataframe-to-dictionary-in-python/)

在本文中，我们将看到如何将 PySpark 数据框转换为字典，其中键是列名，值是列值。

**在开始之前，我们将创建一个示例数据框:**

## python 3

```
# Importing necessary libraries
from pyspark.sql import SparkSession

# Create a spark session
spark = SparkSession.builder.appName('DF_to_dict').getOrCreate()

# Create data in dataframe
data = [(('Ram'), '1991-04-01', 'M', 3000),
        (('Mike'), '2000-05-19', 'M', 4000),
        (('Rohini'), '1978-09-05', 'M', 4000),
        (('Maria'), '1967-12-01', 'F', 4000),
        (('Jenis'), '1980-02-17', 'F', 1200)]

# Column names in dataframe
columns = ["Name", "DOB", "Gender", "salary"]

# Create the spark dataframe
df = spark.createDataFrame(data=data,
                           schema=columns)

# Print the dataframe
df.show()
```