# 如何重命名多个 PySpark 数据框列

> 原文:[https://www . geesforgeks . org/如何重命名-multi-py spark-data frame-columns/](https://www.geeksforgeeks.org/how-to-rename-multiple-pyspark-dataframe-columns/)

在本文中，我们将讨论如何重命名 PySpark Dataframe 中的多个列。为此，我们将使用**和**以及**和**功能。

**创建用于演示的数据框:**

## python 3

```
# importing module
import pyspark

# importing sparksession from pyspark.sql module
from pyspark.sql import SparkSession

# creating sparksession and giving an app name
spark = SparkSession.builder.appName('sparkdf').getOrCreate()

# list  of students  data  with null values
# we can define null values with none
data = [[None, "sravan", "vignan"],
        ["2", None, "vvit"],
        ["3", "rohith", None],
        ["4", "sridevi", "vignan"],
        ["1", None, None],
        ["5", "gnanesh", "iit"]]

# specify column names
columns = ['ID', 'NAME', 'college']

# creating a dataframe from the lists of data
dataframe = spark.createDataFrame(data, columns)

# show columns
print(dataframe.columns)

# display dataframe
dataframe.show()
```