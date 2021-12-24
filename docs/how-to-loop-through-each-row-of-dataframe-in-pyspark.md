# 如何在 PySpark 中循环遍历每一行数据帧？

> 原文:[https://www . geesforgeks . org/如何循环遍历 pyspark 中的每行数据框/](https://www.geeksforgeeks.org/how-to-loop-through-each-row-of-dataframe-in-pyspark/)

在本文中，我们将看到如何在 PySpark 中循环遍历每一行数据帧。遍历每一行有助于我们对 RDD 或数据帧执行复杂的操作。

**创建用于演示的数据框:**

## python 3

```py
# importing necessary libraries
import pyspark
from pyspark.sql import SparkSession

# function to create new SparkSession
def create_session():
    spk = SparkSession.builder \
        .master("local") \
        .appName("employee_profile.com") \
        .getOrCreate()
    return spk

def create_df(spark, data, schema):
    df1 = spark.createDataFrame(data, schema)
    return df1

if __name__ == "__main__":

    # calling function to create SparkSession
    spark = create_session()

    input_data = [(1, "Shivansh", "Data Scientist", "Noida"),
                  (2, "Rishabh", "Software Developer", "Banglore"),
                  (3, "Swati", "Data Analyst", "Hyderabad"),
                  (4, "Amar", "Data Analyst", "Noida"),
                  (5, "Arpit", "Android Developer", "Pune"),
                  (6, "Ranjeet", "Python Developer", "Gurugram"),
                  (7, "Priyanka", "Full Stack Developer", "Banglore")]

    schema = ["Id", "Name", "Job Profile", "City"]

    # calling function to create dataframe
    df = create_df(spark, input_data, schema)

    # retrieving all the elements of
    # the dataframe using collect()
    # Storing in the variable
    data_collect = df.collect()

    df.show()
```