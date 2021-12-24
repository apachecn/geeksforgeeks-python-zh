# 将函数应用于列表的每个元素–Python

> 原文:[https://www . geesforgeks . org/apply-function-to-a-list-python 中的每个元素/](https://www.geeksforgeeks.org/apply-function-to-each-element-of-a-list-python/)

在本文中，我们将学习如何将函数应用于 Python 列表的每个元素。让我们看看将函数应用于列表的每个元素意味着什么:

假设我们有一个整数列表和一个函数，该函数将列表中的每个整数加倍。将函数应用于列表时，函数应该将列表中的所有整数加倍。我们通过以下方式实现这一功能:

1.  [图()](https://www.geeksforgeeks.org/python-map-function/)法。
2.  使用[列出理解。](https://www.geeksforgeeks.org/python-list-comprehension-and-slicing/)
3.  [λ功能](https://www.geeksforgeeks.org/python-lambda/)

## **使用地图()方法**

map()方法接受两个参数:iterables 和 functions，并返回一个 map 对象。我们使用 list()将地图对象转换为列表。

**程序:**

## 蟒蛇 3

```py
def double(integer):
    return integer*2

# driver code
integer_list = [1, 2, 3]

# Map method returns a map object
# so we cast it into list using list()
output_list = list(map(double, integer_list))

print(output_list)
```

**输出:**

```py
[2, 4, 6]
```

**时间复杂度:** O(n)*(应用于列表的函数的 O 复杂度)

## **使用列表理解**

我们使用列表理解在列表的每个元素上调用一个函数，然后在这种情况下将它加倍。

**程序:**

## 蟒蛇 3

```py
def double(integer):
    return integer*2

# driver code
integer_list = [1, 2, 3]

# Calling double method on each integer
# in list using list comprehension.
output_list = [double(i) for i in integer_list]

print(output_list)
```

**输出:**

```py
[2, 4, 6]
```

**时间复杂度:** O(n)*(应用于列表的函数的 O 复杂度)

## 使用λ函数

λ函数也可以用来产生上述功能。Lambda 能够创建一个匿名函数，该函数可以被做得足够适合给定的需求。

**程序:**

## 蟒蛇 3

```py
lst = [1, 2, 3]

ans = []

for x in lst:
    def res(x): return x*2
    ans.append(res(x))

print(ans)
```

**输出:**

```py
[2, 4, 6]
```