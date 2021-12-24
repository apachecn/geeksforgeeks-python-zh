# 从嵌套字典中创建 PySpark 数据框

> 原文:[https://www . geeksforgeeks . org/create-py spark-data frame-from-nested-dictionary/](https://www.geeksforgeeks.org/create-pyspark-dataframe-from-nested-dictionary/)

在本文中，我们将讨论从嵌套字典创建 Pyspark 数据帧。

我们将使用 pyspark 中的 createDataFrame()方法来创建数据帧。为此，我们将使用嵌套字典的列表，并提取该对作为键和值。通过从嵌套字典中提及 items()函数来选择键、值对

```
[Row(**{'': k, **v}) for k,v in data.items()]
```

**示例 1:** Python 程序，用字典中嵌套地址的字典创建学院数据

## 蟒蛇 3

```
# importing module
import pyspark

# importing sparksession from pyspark.sql module
from pyspark.sql import SparkSession
from pyspark.sql import Row

# creating sparksession and giving an app name
spark = SparkSession.builder.appName('sparkdf').getOrCreate()

# creating nested dictionary
data = {
    'student_1': {
        'student id': 7058,
        'country': 'India',
        'state': 'AP',
        'district': 'Guntur'
    },
    'student_2': {
        'student id': 7059,
        'country': 'Srilanka',
        'state': 'X',
        'district': 'Y'
    }
}

# taking row data
rowdata = [Row(**{'': k, **v}) for k,
           v in data.items()]

# creating the pyspark dataframe
final = spark.createDataFrame(rowdata).select(
  'student id', 'country', 'state', 'district')

# display pyspark dataframe
final.show()
```

**输出:**

```
+----------+--------+-----+--------+
|student id| country|state|district|
+----------+--------+-----+--------+
|      7058|   India|   AP|  Guntur|
|      7059|Srilanka|    X|       Y|
+----------+--------+-----+--------+
```

**示例 2:** Python 程序，用于创建具有 3 列(3 个键)的嵌套字典

## 蟒蛇 3

```
# importing module
import pyspark

# importing sparksession from pyspark.sql module
from pyspark.sql import SparkSession
from pyspark.sql import Row

# creating sparksession and giving an app name
spark = SparkSession.builder.appName('sparkdf').getOrCreate()

# creating nested dictionary
data = {
    'student_1': {
        'student id': 7058,
        'country': 'India',
        'state': 'AP'
    },
    'student_2': {
        'student id': 7059,
        'country': 'Srilanka',
        'state': 'X'

    }
}

# taking row data
rowdata = [Row(**{'': k, **v}) for k, v in data.items()]

# creating the pyspark dataframe
final = spark.createDataFrame(rowdata).select(
  'student id', 'country', 'state')

# display pyspark dataframe
final.show()
```

**输出:**

```
+----------+--------+-----+
|student id| country|state|
+----------+--------+-----+
|      7058|   India|   AP|
|      7059|Srilanka|    X|
+----------+--------+-----+
```