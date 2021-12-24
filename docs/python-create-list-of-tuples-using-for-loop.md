# Python–创建用于循环的元组列表

> 原文:[https://www . geesforgeks . org/python-创建元组列表-使用 for 循环/](https://www.geeksforgeeks.org/python-create-list-of-tuples-using-for-loop/)

在本文中，我们将讨论如何使用 Python 中的 for 循环创建元组列表。

假设我们有一个列表，我们希望从该列表中创建一个元组列表，其中元组的每个元素都包含列表元素及其对应的索引。

## 方法 1:使用[进行循环](https://www.geeksforgeeks.org/python-for-loops/)和追加()方法

这里我们将使用 for 循环和 append()方法。我们将遍历列表的元素，并将使用 append() **方法向结果列表添加一个元组。**

**示例:**

## 蟒蛇 3

```
L = [5, 4, 2, 5, 6, 1]
res = []

for i in range(len(L)):
    res.append((L[i], i))

print("List of Tuples")
print(res)
```

**Output**

```
List of Tuples
[(5, 0), (4, 1), (2, 2), (5, 3), (6, 4), (1, 5)]
```

## 方法二:使用 For 循环配合[枚举()方法](https://www.geeksforgeeks.org/enumerate-in-python/)

枚举()方法向 iterable 添加一个计数器，并以枚举对象的形式返回它。所以我们可以使用这个函数来创建期望的元组列表。

**示例:**

## 蟒蛇 3

```
L = [5, 4, 2, 5, 6, 1]
res = []

for index, element in enumerate(L):
    res.append((element, index))

print("List of Tuples")
print(res)
```

**Output**

```
List of Tuples
[(5, 0), (4, 1), (2, 2), (5, 3), (6, 4), (1, 5)]
```