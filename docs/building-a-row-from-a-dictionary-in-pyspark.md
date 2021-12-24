# 在 PySpark 中根据字典建立一行

> 原文:[https://www . geesforgeks . org/building-a-row-from-in-dictionary-in-py spark/](https://www.geeksforgeeks.org/building-a-row-from-a-dictionary-in-pyspark/)

在本文中，我们将讨论如何在 PySpark 中从字典中构建一行

为此，我们将把字典传递给 Row()方法。

**语法:**

> **语法:**行(字典)

**示例 1:** 用键值对(字典)作为参数构建一行。

在这里，我们将通过与字典的行

> **语法:**行({ ' Key ':' value '，' Key ':' value '，' Key ':' value ' })

## 蟒蛇 3

```py
# import Row
from pyspark.sql import Row

# dict
dic = {'First_name':"Sravan", 
       'Last_name':"Kumar",
       'address':"hyderabad"}

# create a row with three values
# as dictionary.
row = Row(dic)

# display row
print(row)
```

**输出:**

**示例 2:** Python 程序用字典构建两行。

> **语法:**行(dict，dict)

**代码:**

## 蟒蛇 3

```py
# import Row
from pyspark.sql import Row

dic_1 = {'First_name':"Sravan", 
         'Last_name':"Kumar",
         'address':"hyderabad"}

dic_2 = {'First_name':"Bobby",
         'Last_name':"Gottumukkala",
         'address':"Ponnur"}

# create two rows with
# three values as dictionary.
row = [Row(dic_1),
       Row(dic_2)]
# display row
print(row)
```

**输出:**

> 【<row>、</row>
> 
> <row>]</row>