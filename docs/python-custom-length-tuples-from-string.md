# Python–来自字符串的自定义长度元组

> 原文:[https://www . geesforgeks . org/python-custom-length-元组-from-string/](https://www.geeksforgeeks.org/python-custom-length-tuples-from-string/)

给定一个字符串，提取元组列表，每个元组都是自定义长度，用逗号分隔。

> **输入**:test _ str =“6 6 7，3 4，2”
> 
> **输出** : [(6，6，7)，(3，4)，(2，]
> 
> **说明**:海关长度为 3、2、1 已转换为元组列表。
> 
> **输入**:test _ str =“7，7，4”
> 
> **输出** : [(7)、(7)、(4、]
> 
> **说明**:所有元素长度为 1。

**方法一:使用 int() + tuple() + split() +列表理解**

上述功能的组合可以用来解决这个问题。在本文中，我们使用 int()和 tuple()执行字符串的转换，并且 split()用于在分隔符上进行拆分。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Custom length tuples from String
# Using int() + tuple() + split() + list comprehension

# initializing string
test_str = '4 6 7, 1 2, 3, 4 6 8 8'

# printing original string
print("The original string is : " + str(test_str))

# split() used to split on delimiter and
# type casted to int followed by tuple casting
test_str = test_str.split(', ')
res = [tuple(int(ele) for ele in sub.split()) for sub in test_str]

# printing result
print("The constructed custom length tuples : " + str(res))
```

**Output**

```py
The original string is : 4 6 7, 1 2, 3, 4 6 8 8
The constructed custom length tuples : [(4, 6, 7), (1, 2), (3, ), (4, 6, 8, 8)]
```

**方法 2:使用 map() + int + tuple() +列表理解+ split()**

上述功能的组合提供了执行该任务的另一种方式。在本例中，我们使用与上面类似的方法执行任务，不同之处在于使用 map()将整数转换的逻辑扩展到元素。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Custom length tuples from String
# Using map() + int + tuple() + list comprehension + split()

# initializing string
test_str = '4 6 7, 1 2, 3, 4 6 8 8'

# printing original string
print("The original string is : " + str(test_str))

# split() used to split on delimiter and
# using map() to extend logic of element casting
res = [tuple(map(int, sub.split())) for sub in test_str.split(", ")]

# printing result
print("The constructed custom length tuples : " + str(res))
```

**Output**

```py
The original string is : 4 6 7, 1 2, 3, 4 6 8 8
The constructed custom length tuples : [(4, 6, 7), (1, 2), (3, ), (4, 6, 8, 8)]
```