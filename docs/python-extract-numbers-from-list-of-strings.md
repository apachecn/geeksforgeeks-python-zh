# Python |从字符串列表中提取数字

> 原文:[https://www . geesforgeks . org/python-从字符串列表中提取数字/](https://www.geeksforgeeks.org/python-extract-numbers-from-list-of-strings/)

有时，我们可以以多种形式获取数据，我们希望对整体的某些特定部分进行转换和提取。一个这样的问题可能是从字符串中提取一个数字并扩展它，有时它可能不仅仅是一个元素字符串，而是它的一个列表。让我们讨论一下解决这个问题的某些方法。

**方法一:使用列表理解+ `split()`**

这个特殊的问题可以通过使用列表理解功能来解决，该功能将逻辑扩展到所有项目，并且拆分功能执行拆分任务并获取目标所需元素。

```
# Python3 code to demonstrate
# Extracting numbers from list of strings
# using list comprehension + split()

# initializing list
test_list = ['Rs. 24', 'Rs. 18', 'Rs. 8', 'Rs. 21']

# printing original list
print("The original list : " + str(test_list))

# using list comprehension + split()
# Extracting numbers from list of strings
res = [int(sub.split('.')[1]) for sub in test_list]

# print result
print("The list after Extracting numbers : " + str(res))
```

**Output :**

```
The original list : ['Rs. 24', 'Rs. 18', 'Rs. 8', 'Rs. 21']
The list after Extracting numbers : [24, 18, 8, 21]

```

**方法二:使用`join() + isnumeric()` +列表理解+`map()`+T3】**

这种方法在没有预先定义数字将按特定方式排序的情况下是优选的，即，这种方法提供了从任何可能的位置获得数字的灵活性。

```
# Python3 code to demonstrate
# Extracting numbers from list of strings
# using join() + isnumeric() + list comprehension + map()

# initializing list
test_list = ['Rs. 24', 'Rs. 18', 'Rs. 8', 'Rs. 21']

# printing original list
print("The original list : " + str(test_list))

# using join() + isnumeric() + list comprehension + map()
# Extracting numbers from list of strings
res = list(map(lambda sub:int(''.join(
      [ele for ele in sub if ele.isnumeric()])), test_list))

# print result
print("The list after Extracting numbers : " + str(res))
```

**Output :**

```
The original list : ['Rs. 24', 'Rs. 18', 'Rs. 8', 'Rs. 21']
The list after Extracting numbers : [24, 18, 8, 21]

```