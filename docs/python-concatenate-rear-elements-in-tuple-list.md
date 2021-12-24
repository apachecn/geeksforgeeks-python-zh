# Python–连接元组列表中的后元素

> 原文:[https://www . geeksforgeeks . org/python-concatenate-后置元素-in-tuple-list/](https://www.geeksforgeeks.org/python-concatenate-rear-elements-in-tuple-list/)

给定元组列表，连接后面的元素。

> **输入** : test_list = [(1，2，“Gfg”)，(“最佳”，)]
> **输出** : Gfg 最佳
> **解释**:最后一个元素加入。
> 
> **输入** : test_list = [(1，2，“Gfg”)]
> **输出** : Gfg
> **解释**:最后一个元素加入。

**方法一:使用列表理解+连接()**

在本文中，我们使用“-1”作为索引来检查最后一个元素，并使用 join()执行连接，使用列表理解来迭代每个元组。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Concatenate Rear elements in Tuple List
# Using join() + list comprehension

# initializing list
test_list = [(1, 2, "Gfg"), (4, "is"), ("Best", )]

# printing original list
print("The original list is : " + str(test_list))

# "-1" is used for access
res = " ".join([sub[-1] for sub in test_list]) 

# printing result 
print("The Concatenated result : " + str(res))
```

**Output**

```
The original list is : [(1, 2, 'Gfg'), (4, 'is'), ('Best', )]
The Concatenated result : Gfg is Best

```

**方法 2:使用 map() + itemgetter() + join()**

在本例中，我们使用 itemgetter(-1)执行获取最后一个元素的任务，使用 map()获取所有最后的元素，使用 join()进行连接。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Concatenate Rear elements in Tuple List
# Using map() + itemgetter() + join()
from operator import itemgetter

# initializing list
test_list = [(1, 2, "Gfg"), (4, "is"), ("Best", )]

# printing original list
print("The original list is : " + str(test_list))

# "-1" is used for access
# map() to get all elements 
res = " ".join(list(map(itemgetter(-1), test_list))) 

# printing result 
print("The Concatenated result : " + str(res))
```

**Output**

```
The original list is : [(1, 2, 'Gfg'), (4, 'is'), ('Best', )]
The Concatenated result : Gfg is Best

```