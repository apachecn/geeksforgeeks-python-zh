# Python |将字符串转换为元组

> 原文:[https://www . geesforgeks . org/python-convert-string-to-tuple/](https://www.geeksforgeeks.org/python-convert-string-to-tuple/)

数据类型的相互转换是编程时可能面临的一个非常常见的问题。可能会有一个问题，我们需要将一串整数转换为一个元组。让我们讨论一下实现这一点的某些方法。

**方法#1:使用`map() + int + split() + tuple()`**
这个方法可以用来解决这个特殊的任务。在这种情况下，我们只需拆分字符串的每个元素并转换为列表，然后将列表转换为结果元组。

```
# Python3 code to demonstrate working of
# Convert String to Tuple
# using map() + tuple() + int + split()

# initialize string
test_str = "1, -5, 4, 6, 7"

# printing original string 
print("The original string : " + str(test_str))

# Convert String to Tuple
# using map() + tuple() + int + split()
res = tuple(map(int, test_str.split(', ')))

# printing result
print("Tuple after getting conversion from String : " + str(res))
```

**Output :**

```
The original string : 1, -5, 4, 6, 7
Tuple after getting conversion from String : (1, -5, 4, 6, 7)

```