# Python–字典值列表长度产品

> 原文:[https://www . geesforgeks . org/python-dictionary-value-list-length-product/](https://www.geeksforgeeks.org/python-dictionary-value-lists-lengths-product/)

给定一个值为列表的字典，计算每个列表的长度，并找到所有长度的乘积。

> **输入** : test_dict = {'Gfg' : [6，5，9，3]，' is' : [1，3，4]，' best' :[9，16]}
> **输出** : 24
> **解释** : 4 * 3 * 2 = 24。列表的长度是 4、3 和 2。
> 
> **输入** : test_dict = {'Gfg' : [6，5，3]，' is' : [1，3，4]，' best' :[9，16]}
> 输出 : 18
> **解释** : 3 * 3 * 2 = 18。列表的长度是 3、3 和 2。

**方法#1:使用 loop + len()**

这是执行这项任务的方法之一。在这种情况下，我们对所有值进行迭代，并使用 len()获得所有值列表的长度，然后执行整个数据的乘法。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Dictionary value lists lengths product
# Using loop + len()

# initializing dictionary
test_dict = {'Gfg' : [6, 5, 9, 3, 10],
             'is' : [1, 3, 4], 
             'best' :[9, 16]}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# using loop to iterate through all keys 
res = 1
for key in test_dict:

    # len() used to get length of each value list
    res = res * len(test_dict[key])    

# printing result 
print("The computed product : " + str(res)) 
```

**Output**

```py
The original dictionary is : {'Gfg': [6, 5, 9, 3, 10], 'is': [1, 3, 4], 'best': [9, 16]}
The computed product : 30

```

**方法 2:使用 map() + lambda + reduce()**

上述功能的组合提供了一种解决这个问题的线性方法。在这种情况下，我们使用 map()来获取所有列表的长度，将 len()扩展到每个列表，lambda 用于获取乘积并减少到组合。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Dictionary value lists lengths product
# Using map() + lambda + reduce() 
from functools import reduce

# initializing dictionary
test_dict = {'Gfg' : [6, 5, 9, 3, 10],
             'is' : [1, 3, 4], 
             'best' :[9, 16]}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# values() used to get all lists of keys
res = reduce(lambda sub1, sub2: sub1 * sub2, map(len, test_dict.values()))

# printing result 
print("The computed product : " + str(res)) 
```

**Output**

```py
The original dictionary is : {'Gfg': [6, 5, 9, 3, 10], 'is': [1, 3, 4], 'best': [9, 16]}
The computed product : 30

```