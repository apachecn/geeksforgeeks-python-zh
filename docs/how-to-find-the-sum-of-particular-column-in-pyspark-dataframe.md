# 如何在 PySpark 数据框中找到特定列的和

> 原文:[https://www . geesforgeks . org/如何找到 pyspark-dataframe 中特定列的总和/](https://www.geeksforgeeks.org/how-to-find-the-sum-of-particular-column-in-pyspark-dataframe/)

在本文中，我们将在 Python 中找到 PySpark 数据框列的总和。我们将使用 agg()函数找到列中的和。

让我们创建一个示例数据帧。

## 蟒 3

```py
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
columns = ['student ID', 'student NAME', 'college',
           'subject 1', 'subject 2']

# creating a dataframe from the lists of data
dataframe = spark.createDataFrame(data, columns)

# display dataframe
dataframe.show()
```