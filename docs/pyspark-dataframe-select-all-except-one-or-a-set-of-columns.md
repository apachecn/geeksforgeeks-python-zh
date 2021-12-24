# PySpark 数据框–选择除一列或一组列之外的所有列

> 原文:[https://www . geesforgeks . org/py spark-data frame-select-all-except-one-or-set-columns/](https://www.geeksforgeeks.org/pyspark-dataframe-select-all-except-one-or-a-set-of-columns/)

在本文中，我们将从 Pyspark 数据框中提取除一组列或一列之外的所有列。为此，我们将使用 select()，drop()函数。

但是首先，让我们为演示创建一个数据框架。

## 蟒 3

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
        ["1", "sravan", "vignan"],
        ["5", "gnanesh", "iit"]]

# specify column names
columns = ['student ID', 'student NAME', 'college']

# creating a dataframe from the lists of data
dataframe = spark.createDataFrame(data, columns)

print('Actual data in dataframe')
dataframe.show()
```