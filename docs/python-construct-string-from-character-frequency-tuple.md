# Python |从字符频率元组构建字符串

> 原文:[https://www . geesforgeks . org/python-construct-string-from-character-frequency-tuple/](https://www.geeksforgeeks.org/python-construct-string-from-character-frequency-tuple/)

有时，在处理数据时，我们可能会遇到这样的问题:我们需要以这样一种方式执行字符串的构造，即我们有一个包含字符及其对应频率的元组列表，并且我们需要从该列表构造一个新的字符串。让我们讨论执行这项任务的某些方法。

**方法#1:使用循环**
这是可以执行该任务的蛮力方法。在本文中，我们迭代列表，并使用*运算符执行字符串连接，并继续以这种方式构建字符串。

```
# Python3 code to demonstrate working of
# String construction from character frequency
# using loop

# initialize list 
test_list = [('g', 4), ('f', 3), ('g', 2)]

# printing original list 
print("The original list : " + str(test_list))

# String construction from character frequency
# using loop
res = ''
for char, freq in test_list:
    res = res + char * freq

# printing result
print("The constructed string is : " + str(res))
```

**Output :**

```
The original list : [('g', 4), ('f', 3), ('g', 2)]
The constructed string is : ggggfffgg

```