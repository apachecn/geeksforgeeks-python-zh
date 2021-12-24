# Python–整数字符串到整数列表

> 原文:[https://www . geesforgeks . org/python-integers-string-to-integer-list/](https://www.geeksforgeeks.org/python-integers-string-to-integer-list/)

给定一个整数字符串，由负数和正数组成，转换为整数列表。

> **输入**:test _ str = ' 4 5-3 2-100-2 '
> **输出** : [4，5，-3，2，-100，-2]
> **解释**:正负串数转换成整数列表。
> 
> **输入**:test _ str = '-4-5-3 2-100-2 '
> **输出** : [-4、-5、-3、2、-100、-2]
> **解释**:正负串数转换成整数列表。

**方法一:使用列表理解+ int() + split()**

在这种情况下，我们使用 split()来分割整数，而 int()用于积分转换。使用列表理解在列表中插入的元素

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Integers String to Integer List
# Using list comprehension + int() + split()
import string

# initializing string
test_str = '4 5 -3 2 -100 -2 -4 9'

# printing original string
print("The original string is : " + str(test_str))

# int() converts to required integers
res = [int(ele) for ele in test_str.split()]

# printing result 
print("Converted Integers : " + str(res)) 
```

**Output**

```py
The original string is : 4 5 -3 2 -100 -2 -4 9
Converted Integers : [4, 5, -3, 2, -100, -2, -4, 9]

```

**方法 2:使用 map() + int()**

在这种情况下，整数转换的逻辑扩展任务是使用 map()完成的。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Integers String to Integer List
# Using map() + int()
import string

# initializing string
test_str = '4 5 -3 2 -100 -2 -4 9'

# printing original string
print("The original string is : " + str(test_str))

# int() converts to required integers
# map() extends logic of int to each split
res = list(map(int, test_str.split()))

# printing result 
print("Converted Integers : " + str(res)) 
```

**Output**

```py
The original string is : 4 5 -3 2 -100 -2 -4 9
Converted Integers : [4, 5, -3, 2, -100, -2, -4, 9]

```