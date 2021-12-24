# Python |字符串元素的笛卡尔乘积

> 原文:[https://www . geeksforgeeks . org/python-笛卡尔-字符串元素乘积/](https://www.geeksforgeeks.org/python-cartesian-product-of-string-elements/)

有时，在使用 Python 字符串时，我们可能会遇到这样的问题，即数据是以逗号或任何 delim 分隔的字符串形式存在的。我们可能希望对其他类似的字符串执行笛卡儿积，以获得所有可能的数据对。让我们讨论执行这项任务的某些方法。

**方法#1:使用列表理解+拆分()**
这个任务可以使用列表理解来执行。在本文中，我们使用 split()执行提取单个元素的任务。列表理解的任务是组成对。

```
# Python3 code to demonstrate working of 
# Cartesian product of string elements
# Using split() + list comprehension

# initializing strings
test_str1 = "gfg, is, best"
test_str2 = "for, all, geeks"

# printing original strings
print("The original string 1 is : " + test_str1)
print("The original string 2 is : " + test_str2)

# Cartesian product of string elements
# Using split() + list comprehension
res = [sub1 + sub2 for sub1 in test_str1.split(", ") for sub2 in test_str2.split(", ")]

# printing result 
print("Cartesian product list : " + str(res)) 
```

**Output :**

```
The original string 1 is : gfg, is, best
The original string 2 is : for, all, geeks
Cartesian product list : ['gfgfor', 'gfgall', 'gfggeeks', 'isfor', 'isall', 'isgeeks', 'bestfor', 'bestall', 'bestgeeks']

```