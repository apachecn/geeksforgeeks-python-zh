# Python–查找元组中给定数据类型的频率

> 原文:[https://www . geesforgeks . org/python-find-给定数据类型在元组中的出现频率/](https://www.geeksforgeeks.org/python-find-frequency-of-given-datatype-in-tuple/)

有时，在处理 Python 记录时，我们可能会遇到一个问题，即我们需要提取元组中出现的任何数据类型的计数。这可以应用于各种领域，如日常编程和网络开发。让我们讨论执行这项任务的某些方法。

> **输入** : test_tuple = (5，' Gfg '，2，8.8，1.2，' is ')，data_type = int
> **输出** : 2
> 
> **输入** : test_tuple = (5，' Gfg '，2，8.8，1.2，' is ')，data_type = str
> **输出** : 2

**方法#1:使用 loop + `isinstance()`**
以上功能的组合可以用来解决这个问题。在本例中，我们使用 isinstance()执行检查数据类型的任务，并运行一个计数器在匹配时递增。

```
# Python3 code to demonstrate working of 
# Data type frequency in tuple
# Using loop + isinstance()

# initializing tuples
test_tuple = (5, 'Gfg', 2, 8.8, 1.2, 'is')

# printing original tuple
print("The original tuple : " + str(test_tuple))

# initializing data type
data_type = float

# Data type frequency in tuple
# Using loop + isinstance()
count = 0
for ele in test_tuple:
    if isinstance(ele, float):
        count = count + 1

# printing result 
print("The data type frequency : " + str(count))
```

**Output :**

```
The original tuple : (5, 'Gfg', 2, 8.8, 1.2, 'is')
The data type frequency : 2

```

**方法二:使用`sum()`+`isinstance()`+**
以上功能的组合也可以用来解决这个问题。这使用了与上述方法类似的求解方式，只是以速记方式使用 sum()进行计数。

```
# Python3 code to demonstrate working of 
# Data type frequency in tuple
# Using sum() + isinstance()

# initializing tuples
test_tuple = (5, 'Gfg', 2, 8.8, 1.2, 'is')

# printing original tuple
print("The original tuple : " + str(test_tuple))

# initializing data type
data_type = float

# Data type frequency in tuple
# Using sum() + isinstance()
count = sum(1 for ele in test_tuple if isinstance(ele, data_type))

# printing result 
print("The data type frequency : " + str(count))
```

**Output :**

```
The original tuple : (5, 'Gfg', 2, 8.8, 1.2, 'is')
The data type frequency : 2

```