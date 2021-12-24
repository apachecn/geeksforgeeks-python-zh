# Python |检查列表列表上的三角不等式

> 原文:[https://www . geeksforgeeks . org/python-checking-trial-不等式-列表中的列表/](https://www.geeksforgeeks.org/python-checking-triangular-inequality-on-list-of-lists/)

给定一个列表列表，任务是找出一个子列表是否满足三角不等式。

**三角形不等式**规定，对于任意三角形，任意两条边的长度之和必须大于或等于剩余边的长度。换句话说，如果三角形的两条边之和大于第三条边，则三角形有效。如果三面是 a、b、c，那么就要满足三个条件。

```py
a + b > c 
a + c > b 
b + c > a  

```

![](img/5982f7eed6fe177c6151109979bdac2a.png)

**方法一:使用列表理解**

```py
# Python code to find whether a sublist 
# satisfies the triangle inequality.

# List initialization
Input = [[1, 3, 1], [4, 5, 6]]

# Sorting sublist
for elem in Input:
    elem.sort()

# Using list comprehension
Output = [(p, q, r) for p, q, r in Input if (p + q)>= r]

# Printing output
print(Output)
```

**Output:**

```py
[(4, 5, 6)]

```

**方法 2:使用迭代**

```py
# Python code to find whether a sublist
# satisfies the triangle inequality.

# List initialization
Input = [[1, 1, 3], [4, 5, 6]]

# Sorting sublist of list of list
for elem in Input:
    elem.sort()

# Checking for triangular inequality
for elem in Input:
    if elem[0] + elem[1] > elem[2]:
        print(elem)
```

**Output:**

```py
[4, 5, 6]

```