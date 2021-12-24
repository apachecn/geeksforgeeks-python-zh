# 在 PySpark

中将行转换为列表 RDD

> 原文:[https://www . geesforgeks . org/converting-row-to-list-rdd-in-py spark/](https://www.geeksforgeeks.org/converting-row-into-list-rdd-in-pyspark/)

在本文中，我们将把 Row 转换成 Pyspark 中的列表 RDD。

从第行创建 RDD 进行演示:

## 第三行

```
# import Row and SparkSession
from pyspark.sql import SparkSession, Row

# create sparksession
spark = SparkSession.builder.appName('SparkByExamples.com').getOrCreate()

# create student data with Row function
data = [Row(name="sravan kumar",
            subjects=["Java", "python", "C++"],
            state="AP"),

        Row(name="Ojaswi",
            lang=["Spark", "Java", "C++"],
            state="Telangana"),

        Row(name="rohith",
            subjects=["DS", "PHP", ".net"],
            state="AP"),

        Row(name="bobby",
            lang=["Python", "C", "sql"],
            state="Delhi"),

        Row(name="rohith",
            lang=["CSharp", "VB"],
            state="Telangana")]
rdd = spark.sparkContext.parallelize(data)

# display actual rdd
rdd.collect()
```