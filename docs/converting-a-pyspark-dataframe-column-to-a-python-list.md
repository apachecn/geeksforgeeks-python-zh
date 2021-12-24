# 将 PySpark 数据框列转换为 Python 列表

> 原文:[https://www . geesforgeks . org/converting-a-pyspark-data frame-column-to-a-python-list/](https://www.geeksforgeeks.org/converting-a-pyspark-dataframe-column-to-a-python-list/)

在本文中，我们将讨论如何将 Pyspark dataframe 列转换为 Python 列表。

**创建用于演示的数据框:**

## python 3

```
# importing module
import pyspark

# importing sparksession from pyspark.sql module
from pyspark.sql import SparkSession

# creating sparksession and giving an app name
spark = SparkSession.builder.appName('sparkdf').getOrCreate()

# list  of students  data
data = [["1", "sravan", "vignan", 67, 89],
        ["2", "ojaswi", "vvit", 78, 89],
        ["3", "rohith", "vvit", 100, 80],
        ["4", "sridevi", "vignan", 78, 80],
        ["1", "sravan", "vignan", 89, 98],
        ["5", "gnanesh", "iit", 94, 98]]

# specify column names
columns = ['student ID', 'student NAME',
           'college', 'subject1', 'subject2']

# creating a dataframe from the lists of data
dataframe = spark.createDataFrame(data, columns)

# display dataframe
dataframe.show()
```