# Pyspark 数据框–将字符串映射到数字

> 原文:[https://www . geesforgeks . org/py spark-data frame-map-strings-to-numeric/](https://www.geeksforgeeks.org/pyspark-dataframe-map-strings-to-numeric/)

在本文中，我们将看到如何将映射字符串转换为数字。

#### 正在创建用于演示的数据框:

这里我们为学院名创建一行数据，然后传递 createdataframe()方法，然后显示 dataframe。

## 蟒 3

```py
# importing module
import pyspark

# importing sparksession from pyspark.sql module and Row module
from pyspark.sql import SparkSession,Row

# creating sparksession and giving an app name
spark = SparkSession.builder.appName('sparkdf').getOrCreate()

# list  of college data
dataframe = spark.createDataFrame([Row("vignan"),
                                   Row("rvrjc"),
                                   Row("klu"),
                                   Row("rvrjc"),
                                   Row("klu"),
                                   Row("vignan"),
                                   Row("iit")],
                                  ["college"])

# display dataframe
dataframe.show()
```