# Python–提取元素在范围内的元组

> 原文:[https://www . geesforgeks . org/python-extract-元组-带范围内元素/](https://www.geeksforgeeks.org/python-extract-tuples-with-elements-in-range/)

给定元组列表，提取元素在范围内的元组。

> **输入** : test_list = [(4，5，7)，(5，6)，(3，8，10)，(4，10)]，strt，end = 5，6
> **输出** : [(5，6)]
> **解释**:5-6 范围内只有 1 个元组。
> 
> **输入** : test_list = [(4，5，7)，(5，6)，(3，8，10)，(4，10)]，strt，end = 1，10
> **输出** : [(4，5，7)，(5，6)，(3，8，10)，(4，10)]
> **解释**:均在规定范围内。

**方法一:使用列表理解+ all()**

在本例中，我们使用比较运算符检查范围内的所有元素，对于包含指定范围内元组的元组，all()返回 true。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Extract tuples with elements in Range
# Using all() + list comprehension

# initializing list
test_list = [(4, 5, 7), (5, 6), (3, 8, 10 ), (4, 10)]

# printing original list
print("The original list is : " + str(test_list))

# initializing range 
strt, end = 4, 7

# list comprehension to encapsulate in 1 liner 
# all() checks for all elements in range 
res = [sub for sub in test_list if all(ele >= strt and ele <= end for ele in sub)]

# printing results
print("Filtered tuples : " + str(res))
```

**Output**

```
The original list is : [(4, 5, 7), (5, 6), (3, 8, 10), (4, 10)]
Filtered tuples : [(4, 5, 7), (5, 6)]

```

**方法 2:使用滤镜()+ lambda + all()**

在这种情况下，我们根据 lambda 提供的函数，使用 filter()来提取元组，并使用 all()作为工具来测试范围元组中的所有元素。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Extract tuples with elements in Range
# Using filter() + lambda + all() 

# initializing list
test_list = [(4, 5, 7), (5, 6), (3, 8, 10 ), (4, 10)]

# printing original list
print("The original list is : " + str(test_list))

# initializing range 
strt, end = 4, 7

# list() to get back result as list  
# all() checks for all elements in range 
res = list(filter(lambda sub : all(ele >= strt and ele <= end for ele in sub), test_list))

# printing results
print("Filtered tuples : " + str(res))
```

**Output**

```
The original list is : [(4, 5, 7), (5, 6), (3, 8, 10), (4, 10)]
Filtered tuples : [(4, 5, 7), (5, 6)]

```