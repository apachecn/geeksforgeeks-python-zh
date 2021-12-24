# Python–在集合中添加多个元素

> 原文:[https://www . geesforgeks . org/python-append-多元素集合/](https://www.geeksforgeeks.org/python-append-multiple-elements-in-set/)

在本文中，给定一个元素集和元素列表，任务是编写一个 Python 程序，一次在元素集中追加多个元素。

**示例:**

> **输入:** test_set = {6，4，2，7，9}，up_ele = [1，5，10]
> 
> **输出:** {1，2，4，5，6，7，9，10}
> 
> **说明:**所有元素都被更新和重新排序。(5 在第三位置)。
> 
> **输入:** test_set = {6，4，2，7，9}，up_ele = [1，5，8]
> 
> **输出:** {1，2，4，5，6，7，8，9，10}
> 
> **说明:**所有元素都被更新和重新排序。(第 7 位 8 个)。

**方法#1:使用** [**更新()**](https://www.geeksforgeeks.org/python-set-update/)

在这种情况下，我们使用内置的 update()来使列表中的所有元素与现有的集合对齐。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Append Multiple elements in set
# Using update()

# initializing set
test_set = {6, 4, 2, 7, 9}

# printing original set
print("The original set is : " + str(test_set))

# initializing adding elements
up_ele = [1, 5, 10]

# update() appends element in set
# internally reorders
test_set.update(up_ele)

# printing result
print("Set after adding elements : " + str(test_set))
```

**输出:**

```
The original set is : {2, 4, 6, 7, 9}
Set after adding elements : {1, 2, 4, 5, 6, 7, 9, 10}
```

**方法 2:使用|运算符(管道运算符)**

管道操作符在内部调用 union()，它可以用来执行用较新的元素更新集合的任务。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Append Multiple elements in set
# Using | operator ( Pipe operator )

# initializing set
test_set = {6, 4, 2, 7, 9}

# printing original set
print("The original set is : " + str(test_set))

# initializing adding elements
up_ele = [1, 5, 10]

# | performing task of updating
test_set |= set(up_ele)

# printing result
print("Set after adding elements : " + str(test_set))
```

**输出:**

```
The original set is : {2, 4, 6, 7, 9}
Set after adding elements : {1, 2, 4, 5, 6, 7, 9, 10}
```