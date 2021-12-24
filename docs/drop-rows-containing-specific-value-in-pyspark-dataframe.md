# 删除 PySpark 数据框中包含特定值的行

> 原文:[https://www . geesforgeks . org/drop-row-包含特定值的 pyspark-dataframe/](https://www.geeksforgeeks.org/drop-rows-containing-specific-value-in-pyspark-dataframe/)

在本文中，我们将删除 pyspark dataframe 中具有特定值的行。

**创建用于演示的数据框:**

## python 3

```py
# importing module
import pyspark

# importing sparksession from pyspark.sql module
from pyspark.sql import SparkSession

# creating sparksession and giving an app name
spark = SparkSession.builder.appName('sparkdf').getOrCreate()

# list  of students  data
data = [["1", "sravan", "vignan"],
        ["2", "ojaswi", "vvit"],
        ["3", "rohith", "vvit"],
        ["4", "sridevi", "vignan"],
        ["6", "ravi", "vrs"],
        ["5", "gnanesh", "iit"]]

# specify column names
columns = ['ID', 'NAME', 'college']

# creating a dataframe from the lists of data
dataframe = spark.createDataFrame(data, columns)

print('Actual data in dataframe')
dataframe.show()
```