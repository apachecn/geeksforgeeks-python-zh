# 从字典中创建 PySpark 数据框

> 原文:[https://www . geesforgeks . org/create-py spark-data frame-from-dictionary/](https://www.geeksforgeeks.org/create-pyspark-dataframe-from-dictionary/)

在本文中，我们将讨论从字典中创建 Pyspark 数据框。为此，使用了 spark.createDataFrame()方法。此方法接受两个参数数据和列。数据属性将包含数据框，列属性将包含列名列表。

**示例 1:** Python 代码创建学生地址详细信息并将其转换为数据框

## Python 3

```py
# importing module
import pyspark

# importing sparksession from 
# pyspark.sql module
from pyspark.sql import SparkSession

# creating sparksession and giving 
# an app name
spark = SparkSession.builder.appName('sparkdf').getOrCreate()

# list  of college data with  dictionary
data = [{'student_id': 12, 'name': 'sravan',
         'address': 'kakumanu'}]

# creating a dataframe
dataframe = spark.createDataFrame(data)

# show data frame
dataframe.show()
```