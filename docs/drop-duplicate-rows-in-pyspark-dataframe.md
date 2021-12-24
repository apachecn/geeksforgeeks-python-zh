# 删除 PySpark 数据框中的重复行

> 原文:[https://www . geesforgeks . org/drop-reply-row-in-py spark-data frame/](https://www.geeksforgeeks.org/drop-duplicate-rows-in-pyspark-dataframe/)

在本文中，我们将使用 Python 中的 pyspark，通过使用 dataframe 中的 **distinct()** 和 **dropDuplicates()** 函数来删除重复的行。

让我们创建一个示例数据框

## python 3

```
# importing module
import pyspark

# importing sparksession from
# pyspark.sql module
from pyspark.sql import SparkSession

# creating sparksession and giving
# an app name
spark = SparkSession.builder.appName('sparkdf').getOrCreate()

# list  of employee data
data = [["1", "sravan", "company 1"],
        ["2", "ojaswi", "company 1"],
        ["3", "rohith", "company 2"],
        ["4", "sridevi", "company 1"],
        ["1", "sravan", "company 1"],
        ["4", "sridevi", "company 1"]]

# specify column names
columns = ['Employee ID', 'Employee NAME', 'Company']

# creating a dataframe from the
# lists of data
dataframe = spark.createDataFrame(data, columns)

print('Actual data in dataframe')
dataframe.show()
```