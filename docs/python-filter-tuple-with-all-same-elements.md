# Python–过滤所有相同元素的元组

> 原文:[https://www . geesforgeks . org/python-filter-tuple-with-all-same-elements/](https://www.geeksforgeeks.org/python-filter-tuple-with-all-same-elements/)

给定元组列表，过滤具有相同值的元组。

> **输入** : test_list = [(5，6，5，5)，(6，6)，(9，10)]
> **输出** : [(6，6，6)]
> **解释** : 1 个相同元素的元组。
> 
> **输入** : test_list = [(5，6，5，5)，(6，5，6)，(9，10)]
> **输出** : []
> **解释**:没有相同元素的元组。

**方法一:使用列表理解+ set() + len()**

在这种情况下，我们检查转换后的元组集的长度是否为 1，如果为 1，则将元组添加到结果中，否则省略。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Filter similar elements Tuples
# Using list comprehension + set() + len()

# initializing list
test_list = [(5, 6, 5, 5), (6, 6, 6), (1, 1), (9, 10)]

# printing original list
print("The original list is : " + str(test_list))

# length is computed using len()
res = [sub for sub in test_list if len(set(sub)) == 1]

# printing results
print("Filtered Tuples : " + str(res))
```

**Output**

```
The original list is : [(5, 6, 5, 5), (6, 6, 6), (1, 1), (9, 10)]
Filtered Tuples : [(6, 6, 6), (1, 1)]
```

**方法 2:使用滤镜()+λ+set()+len()**

在本文中，我们使用 filter()执行过滤任务，并使用 set()和 len()在 lambda 函数中检查单元素逻辑。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Filter similar elements Tuples
# Using filter() + lambda + set() + len()

# initializing list
test_list = [(5, 6, 5, 5), (6, 6, 6), (1, 1), (9, 10)]

# printing original list
print("The original list is : " + str(test_list))

# end result converted to list object
# filter extracts req. tuples
res = list(filter(lambda sub : len(set(sub)) == 1, test_list))

# printing results
print("Filtered Tuples : " + str(res))
```

**Output**

```
The original list is : [(5, 6, 5, 5), (6, 6, 6), (1, 1), (9, 10)]
Filtered Tuples : [(6, 6, 6), (1, 1)]
```