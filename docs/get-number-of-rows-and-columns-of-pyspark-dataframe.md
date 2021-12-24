# 获取 PySpark 数据帧的行数和列数

> 原文:[https://www . geeksforgeeks . org/get-行数和列数-pyspark-dataframe/](https://www.geeksforgeeks.org/get-number-of-rows-and-columns-of-pyspark-dataframe/)

在本文中，我们将讨论如何获取 PySpark 数据帧的行数和列数。为了找到行数和列数，我们将分别使用带有 len()函数的 count()和 columns()。

*   **df.count ():** This function is used to extract the number of rows from a data frame.
*   **df.distinct()。 Count ():** This function is used to extract different rows that are not duplicated/duplicated in the data frame.
*   **df.columns ():** This function is used to extract the list of column names existing in the data frame.
*   **len (df.columns):** This function is used to count the number of items in the list.

**例 1:获取 pyspark 中数据帧的** **行数和列数。**

## 巨蟒

```
# importing necessary libraries
from pyspark.sql import SparkSession

# function to create SparkSession
def create_session():
  spk = SparkSession.builder \
      .master("local") \
      .appName("Products.com") \
      .getOrCreate()
  return spk

# function to create Dataframe
def create_df(spark,data,schema):
  df1 = spark.createDataFrame(data,schema)
  return df1

# main function
if __name__ == "__main__":

  # calling function to create SparkSession
  spark = create_session()

  input_data = [(1,"Direct-Cool Single Door Refrigerator",12499),
          (2,"Full HD Smart LED TV",49999),
          (3,"8.5 kg Washing Machine",69999),
          (4,"T-shirt",1999),
          (5,"Jeans",3999),
          (6,"Men's Running Shoes",1499),
          (7,"Combo Pack Face Mask",999)]

  schm = ["Id","Product Name","Price"]

  # calling function to create dataframe
  df = create_df(spark,input_data,schm)
  df.show()

  # extracting number of rows from the Dataframe
  row = df.count()

  # extracting number of columns from the Dataframe
  col = len(df.columns)

  # printing
  print(f'Dimension of the Dataframe is: {(row,col)}')
  print(f'Number of Rows are: {row}')
  print(f'Number of Columns are: {col}')
```