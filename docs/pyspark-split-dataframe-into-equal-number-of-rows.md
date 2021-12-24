# PySpark–将数据框分割成相等数量的行

> 原文:[https://www . geesforgeks . org/pyspark-split-data frame-in-equal-行数/](https://www.geeksforgeeks.org/pyspark-split-dataframe-into-equal-number-of-rows/)

当有一个巨大的数据集时，最好将它们分成相等的块，然后分别处理每个数据帧。如果数据框上的操作独立于行，这是可能的。然后，可以并行处理每个数据块或同等分割的数据帧，从而更有效地利用资源。在本文中，我们将讨论如何将 PySpark 数据帧拆分成相等数量的行。

**创建数据框进行演示:**

## Python

```
# importing module
import pyspark

# importing sparksession from pyspark.sql module
from pyspark.sql import SparkSession

# creating sparksession and giving an app name
spark = SparkSession.builder.appName('sparkdf').getOrCreate()

# Column names for the dataframe
columns = ["Brand", "Product"]

# Row data for the dataframe
data = [
    ("HP", "Laptop"),
    ("Lenovo", "Mouse"),
    ("Dell", "Keyboard"),
    ("Samsung", "Monitor"),
    ("MSI", "Graphics Card"),
    ("Asus", "Motherboard"),
    ("Gigabyte", "Motherboard"),
    ("Zebronics", "Cabinet"),
    ("Adata", "RAM"),
    ("Transcend", "SSD"),
    ("Kingston", "HDD"),
    ("Toshiba", "DVD Writer")
]

# Create the dataframe using the above values
prod_df = spark.createDataFrame(data=data,
                                schema=columns)

# View the dataframe
prod_df.show()
```