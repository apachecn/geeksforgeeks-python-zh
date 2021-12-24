# 如何重命名 PySpark 数据框中的多列？

> 原文:[https://www . geesforgeks . org/如何重命名-多列-in-pyspark-dataframe/](https://www.geeksforgeeks.org/how-to-rename-multiple-columns-in-pyspark-dataframe/)

在本文中，我们将看到如何重命名 PySpark Dataframe 中的多个列。

**在开始之前，让我们使用 pyspark 创建一个数据帧:**

## python 3

```py
# importing module
import pyspark
from pyspark.sql.functions import col

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

print("Actual data in dataframe")

# show dataframe
dataframe.show()
```