# Python |从元组列表中找到包含给定元素的元组

> 原文:[https://www . geesforgeks . org/python-从元组列表中找到包含给定元素的元组/](https://www.geeksforgeeks.org/python-find-the-tuples-containing-the-given-element-from-a-list-of-tuples/)

给定一个元组列表，任务是找到包含给定元素的所有元组，比如 *n* 。
**例:**

> **输入:** n = 11，list = [(11，22)，(33，55)，(55，77)，(11，44)】
> **输出:**【(11，22)，(11，44)】
> **输入:** n = 3，list = [(14，3)，(23，41)，(33，62)，(1，3)，(3，3)】
> **输出:** [(14，3]

有多种方法可以从元组列表中找到包含给定元素的元组。让我们来看看完成这项任务的一些 Pythonic 方法。
**方法二:**使用列表理解。只有当每个列表中有固定数量的元素时，它才起作用。例如下面代码中的 2 个元素。

## 蟒蛇 3

```py
# Python code to find the tuples containing
# the given element from a list of tuples

# List of tuples
Input = [(14, 3),(23, 41),(33, 62),(1, 3),(3, 3)]

# Find an element in list of tuples.
Output = [item for item in Input
          if item[0] == 3 or item[1] == 3]

# printing output
print(Output)
```

**Output:** 

```py
[(14, 3), (1, 3), (3, 3)]
```

**方法#1 :** 使用过滤器在这个解决方案中，列表中可以有可变数量的节点。

## 蟒蛇 3

```py
# Python code to find the tuples containing
# the given element from a list of tuples

# List of tuples
Input = [(11, 22), (33, 55), (55, 77),
         (11, 44), (33, 22, 100, 11), (99, 11)]

# Using filter
Output = list(filter(lambda x:11 in x, Input))

# Printing output
print(Output)
```

**Output:** 

```py
[(11, 22), (11, 44), (33, 22, 100, 11), (99, 11)]
```