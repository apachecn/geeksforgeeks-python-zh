# 如何创建一个空的 PySpark 数据帧？

> 原文:[https://www . geeksforgeeks . org/如何创建空 pyspark-dataframe/](https://www.geeksforgeeks.org/how-to-create-an-empty-pyspark-dataframe/)

在本文中，我们将看到如何创建一个空的 PySpark 数据帧。空 Pysaprk 数据框是不包含数据的数据框，可以指定也可以不指定数据框的架构。

### **创建一个没有模式的空 RDD**

我们将首先通过指定一个空模式来创建一个**空 RDD** 。

*   **emptyRDD()** 方法创建没有任何数据的 RDD。
*   **createDataFrame()** 方法使用数据帧的指定数据和架构创建 pyspark 数据帧。

**代码:**

## 蟒蛇 3

```
# Import necessary libraries
from pyspark.sql import SparkSession
from pyspark.sql.types import *

# Create a spark session
spark = SparkSession.builder.appName('Empty_Dataframe').getOrCreate()

# Create an empty RDD
emp_RDD = spark.sparkContext.emptyRDD()

# Create empty schema
columns = StructType([])

# Create an empty RDD with empty schema
data = spark.createDataFrame(data = emp_RDD,
                             schema = columns)

# Print the dataframe
print('Dataframe :')
data.show()

# Print the schema
print('Schema :')
data.printSchema()
```

**输出:**

```
Dataframe :
++
||
++
++

Schema :
root
```

### **用模式创建 emptyRDD】**

有可能我们不会得到一个文件进行处理。但是，我们仍然必须用适当的模式手动创建一个数据帧。

*   将数据框的**模式**指定为**列= [“姓名”、“年龄”、“性别”]** 。
*   创建一个空的 RDD，其预期模式为“T1”。

**代码:**

## 蟒蛇 3

```
# Import necessary libraries
from pyspark.sql import SparkSession
from pyspark.sql.types import *

# Create a spark session
spark = SparkSession.builder.appName('Empty_Dataframe').getOrCreate()

# Create an empty RDD
emp_RDD = spark.sparkContext.emptyRDD()

# Create an expected schema
columns = StructType([StructField('Name',
                                  StringType(), True),
                    StructField('Age',
                                StringType(), True),
                    StructField('Gender',
                                StringType(), True)])

# Create an empty RDD with expected schema
df = spark.createDataFrame(data = emp_RDD,
                           schema = columns)

# Print the dataframe
print('Dataframe :')
df.show()

# Print the schema
print('Schema :')
df.printSchema()
```

**输出:**

```
Dataframe :
+----+---+------+
|Name|Age|Gender|
+----+---+------+
+----+---+------+

Schema :
root
 |-- Name: string (nullable = true)
 |-- Age: string (nullable = true)
 |-- Gender: string (nullable = true)
```

### **创建没有模式的空数据框**

*   创建一个**空模式**作为**列**。
*   在 **CreateDataFrame()** 方法中将**数据**指定为**空([])** ，将**模式**指定为**列**。

**代码:**

## 蟒蛇 3

```
# Import necessary libraries
from pyspark.sql import SparkSession
from pyspark.sql.types import *

# Create a spark session
spark = SparkSession.builder.appName('Empty_Dataframe').getOrCreate()

# Create an empty schema
columns = StructType([])

# Create an empty dataframe with empty schema
df = spark.createDataFrame(data = [],
                           schema = columns)

# Print the dataframe
print('Dataframe :')
df.show()

# Print the schema
print('Schema :')
df.printSchema()
```

**输出:**

```
Dataframe :
++
||
++
++

Schema :
root
```

### **用模式**创建一个空数据帧

*   将**数据框**的**模式**指定为**列= [“姓名”、“年龄”、“性别”]** 。
*   在 **CreateDataFrame()** 方法中将**数据指定为空([])** ，将**模式**指定为**列**。

**代码:**

## 蟒蛇 3

```
# Import necessary libraries
from pyspark.sql import SparkSession
from pyspark.sql.types import *

# Create a spark session
spark = SparkSession.builder.appName('Empty_Dataframe').getOrCreate()

# Create an expected schema
columns = StructType([StructField('Name',
                                  StringType(), True),
                    StructField('Age',
                                StringType(), True),
                    StructField('Gender',
                                StringType(), True)])

# Create a dataframe with expected schema
df = spark.createDataFrame(data = [],
                           schema = columns)

# Print the dataframe
print('Dataframe :')
df.show()

# Print the schema
print('Schema :')
df.printSchema()
```

**输出:**

```
Dataframe :
+----+---+------+
|Name|Age|Gender|
+----+---+------+
+----+---+------+

Schema :
root
 |-- Name: string (nullable = true)
 |-- Age: string (nullable = true)
 |-- Gender: string (nullable = true)
```