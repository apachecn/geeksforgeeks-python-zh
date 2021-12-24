# Python |检查一个列表是否包含在另一个列表中

> 原文:[https://www . geesforgeks . org/python-检查列表是否包含在另一个列表中/](https://www.geeksforgeeks.org/python-check-if-a-list-is-contained-in-another-list/)

给定两个列表 A 和 B，编写一个 Python 程序来检查列表 A 是否包含在列表 B 中，而不会破坏列表 A 的顺序。

**示例:**

```
Input : A = [1, 2], B = [1, 2, 3, 1, 1, 2, 2]
Output : True

Input : A = ['x', 'y', 'z'], B = ['x', 'a', 'y', 'x', 'b', 'z']
Output : False

```

**进场#1 :** 幼稚进场

一个简单的方法是使用两个 for 循环，检查整个列表 A 是否包含在列表 B 中。如果在列表 A 中符合这样的位置，则打破循环并返回 true，否则返回 false

```
# Python3 program to Check if a list is 
# contained in another list without breaking order

def removeElements(A, B):
    for i in range(len(B)-len(A)+1):
        for j in range(len(A)):
            if B[i + j] != A[j]:
                break
        else:
            return True
    return False

# Driver code
A = [1, 2]
B = [1, 2, 3, 1, 1, 2, 2]
print(removeElements(A, B))
```

**Output:**

```
True

```

**方法 2 :** 列表理解

更有效的方法是使用列表理解。我们首先用长度为 a 的“n”初始化。现在使用一个 for 循环直到 *len(B)-n* ，并在每次迭代中检查是否`A == B[i:i+n]`。

```
# Python3 program to Remove elements of 
# list that repeated less than k times

def removeElements(A, B):
    n = len(A)
    return any(A == B[i:i + n] for i in range(len(B)-n + 1))

# Driver code
A = [1, 2]
B = [1, 2, 3, 1, 1, 2, 2]
print(removeElements(A, B))
```

**Output:**

```
True

```

**进场#3 :** 使用*加入*和*地图*模块

这里我们使用*连接*将两个列表连接到字符串，然后使用运算符中的*检查列表 A 是否包含在 B 中。*

```
# Python3 program to Remove elements of 
# list that repeated less than k times

def removeElements(A, B):
    return ', '.join(map(str, A)) in ', '.join(map(str, B))

# Driver code
A = ['x', 'y', 'z']
B = ['x', 'a', 'y', 'x', 'b', 'z']
print(removeElements(A, B))
```

**Output:**

```
False

```