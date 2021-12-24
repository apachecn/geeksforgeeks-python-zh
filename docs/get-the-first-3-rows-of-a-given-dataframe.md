# 获取给定数据帧的前 3 行

> 原文:[https://www . geeksforgeeks . org/获取给定数据框的前 3 行/](https://www.geeksforgeeks.org/get-the-first-3-rows-of-a-given-dataframe/)

让我们首先创建一个数据帧，然后我们将尝试使用几种方法获取该数据帧的前 3 行。

**代码:**创建数据框。

## 蟒 3

```py
# import pandas library
import pandas as pd

# dictionary
record = {
  "Name": ["Tom", "Jack", "Lucy",
           "Bob", "Jerry", "Alice",
           "Thomas", "Barbie"],

   "Marks": [9, 19, 20, 
             17, 11, 18,
             5, 8], 

  "Status": ["Fail", "Pass", "Pass",
             "Pass","Pass", "Pass",
             "Fail", "Fail"]}

# converting record into
# pandas dataframe
df = pd.DataFrame(record)

# printing whole dataframe
df
```