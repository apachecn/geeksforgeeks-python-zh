# Python–列表中的替代最小元素

> 原文:[https://www . geesforgeks . org/python-alternate-最小列表元素/](https://www.geeksforgeeks.org/python-alternate-minimum-element-in-list/)

有些列表操作非常普通，不需要编写多行代码就能快速完成。想要构建由原始列表的所有替代元素组成的列表是一个开发人员在日常应用程序中面临的问题，有时需要找到这些替代元素的最小值。让我们讨论一下实现这一点的某些方法。

**方法#1:使用列表理解+ min()**
简单方法的简写，列表理解提供了一种更快的方式来执行这个特定的任务。在这种方法中，所有不是 2 的倍数(因此是奇数)的索引都被插入到新列表中。然后使用 min()提取最小值。

## 蟒蛇 3

```py
# Python code to demonstrate
# Alternate elements Minimum
# using list comprehension + min()

# initializing list
test_list = [1, 4, 6, 7, 9, 3, 5]

# printing original list
print ("The original list : " + str(test_list))

# using list comprehension + min()
# Alternate elements Minimum
res = min([test_list[i] for i in range(len(test_list)) if i % 2 != 0])

# printing result
print ("The alternate element list minimum is : " + str(res))
```

**Output : **

```py
The original list : [1, 4, 6, 7, 9, 3, 5]
The alternate element list minimum is : 3
```

**方法 2:使用 enumerate() + min()**
这只是列表理解方法的一种变体，但与列表理解的内部工作方式类似，但使用不同的变量来跟踪索引及其值。然后使用 min()提取最小值。

## 蟒蛇 3

```py
# Python code to demonstrate
# Alternate elements Minimum
# using enumerate() + min()

# initializing list
test_list = [1, 4, 6, 7, 9, 3, 5]

# printing original list
print ("The original list : " + str(test_list))

# using enumerate() + min()
# Alternate elements Minimum
res = min([i for j, i in enumerate(test_list) if j % 2 != 0])

# printing result
print ("The alternate element list minimum is : " + str(res))
```

**Output : **

```py
The original list : [1, 4, 6, 7, 9, 3, 5]
The alternate element list minimum is : 3
```