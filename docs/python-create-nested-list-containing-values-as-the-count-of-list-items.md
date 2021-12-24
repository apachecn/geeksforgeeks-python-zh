# Python–创建包含值的嵌套列表作为列表项目的计数

> 原文:[https://www . geesforgeks . org/python-create-nested-list-包含列表项计数的值/](https://www.geeksforgeeks.org/python-create-nested-list-containing-values-as-the-count-of-list-items/)

给定一个列表，任务是编写一个 Python 程序来创建一个嵌套列表，其中的值是列表项的计数。

**示例:**

```
Input: [1, 2, 3]
Output: [[1], [2, 2], [3, 3, 3]]

Input: [4, 5]
Output: [[1, 1, 1, 1], [2, 2, 2, 2, 2]]
```

**方法一:使用嵌套** [**列表理解**](https://www.geeksforgeeks.org/python-list-comprehension-and-slicing/)

该列表将包含列表中每个元素 e 的列表项计数，我们将在列表中创建一个大小为 e 的列表，在每个列表中，我们将为 e 次添加元素 e。

## 蟒蛇 3

```
l = [1, 2, 3, 4, 5]
l = [[i+1 for j in range(l[i])] for i in range(len(l))]
print(l)
```

**输出:**

```
[[1], [2, 2], [3, 3, 3], [4, 4, 4, 4], [5, 5, 5, 5, 5]]
```

**方法二:**

该列表将包含列表项的计数，该计数重复循环 L 次，即列表的长度。现在在每个元素上附加一个列表，附加的列表将是大小计数。

## 蟒蛇 3

```
l = [1, 2, 3, 4, 5]

for i in range(len(l)):
    l[i] = [i+1 for j in range(i+1)]

print(l)
```

**输出:**

```
[[1], [2, 2], [3, 3, 3], [4, 4, 4, 4], [5, 5, 5, 5, 5]]
```