# 如何检查 PySpark 数据框是否为空？

> 原文:[https://www . geesforgeks . org/how-check-if-py spark-data frame-为空/](https://www.geeksforgeeks.org/how-to-check-if-pyspark-dataframe-is-empty/)

在本文中，我们将检查 Pyspark 数据框或数据集是否为空。

首先，让我们创建一个数据框

## python 3

```
# import modules
from pyspark.sql import SparkSession
from pyspark.sql.types import StructType, StructField, StringType

# defining schema
schema = StructType([
    StructField('COUNTRY', StringType(), True),
    StructField('CITY', StringType(), True),
    StructField('CAPITAL', StringType(), True)
])

# Create Spark Object
spark = SparkSession.builder.appName("TestApp").getOrCreate()

# Create Empty DataFrame with Schema.
df = spark.createDataFrame([], schema)

# Show schema and data
df.printSchema()
df.show(truncate=False)
```