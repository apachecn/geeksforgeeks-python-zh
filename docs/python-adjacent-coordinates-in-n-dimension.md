# Python–N 维相邻坐标

> 原文:[https://www . geesforgeks . org/python-邻近坐标 n 维/](https://www.geeksforgeeks.org/python-adjacent-coordinates-in-n-dimension/)

有时，在使用 Python Matrix 时，我们可能会遇到一个问题，需要提取给定坐标的所有相邻坐标。这类问题可以应用于许多领域，如 web 开发和学校编程。让我们讨论执行这项任务的特定方式。

> **输入** : test_tup = (1，2，3)
> **输出** : [[0，1，2]，[0，1，3]，[0，1，4]，[0，2，2]，[0，2，3]，[0，3，2]，[0，3，3]，[0，3，4]，[1，1，2]，[1，1，3]，[1，1，4] 2，3]，[2，2，4]，[2，3，2]，[2，3，3]，[2，3，4]]
> **输入** : test_tup = (5，6)
> **输出** : [[4，5]，[4，6]，[4，7]，[5，5]，[5，6]，[5，7]，[6，5]，[6，6]，[6，7]]

**方法:使用递归+ `yield`**
以上功能的组合可以用来解决这个问题。在这种情况下，我们使用查询坐标周围的坐标的 yield 动态提取元素，并使用递归对下一列和下一行进行处理。

```
# Python3 code to demonstrate working of 
# Adjacent Coordinates in N dimension
# Using recursion + yield

# helper_fnc
def adjac(ele, sub = []):
  if not ele:
     yield sub
  else:
     yield from [idx for j in range(ele[0] - 1, ele[0] + 2)
                for idx in adjac(ele[1:], sub + [j])]

# initializing tuple
test_tup = (3, 4)

# printing original tuple
print("The original tuple : " + str(test_tup))

# Initialize dictionary keys with Matrix
# Using deepcopy()
res = list(adjac(test_tup))

# printing result 
print("The adjacent Coordinates : " + str(res)) 
```

**Output :**

```
The original tuple : (3, 4)
The adjacent Coordinates : [[2, 3], [2, 4], [2, 5], [3, 3], [3, 4], [3, 5], [4, 3], [4, 4], [4, 5]]

```