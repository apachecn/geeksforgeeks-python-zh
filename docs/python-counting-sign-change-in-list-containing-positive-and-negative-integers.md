# Python |包含正负整数的列表中计数符号变化

> 原文:[https://www . geesforgeks . org/python-counting-sign-in-change-list-包含正负整数/](https://www.geeksforgeeks.org/python-counting-sign-change-in-list-containing-positive-and-negative-integers/)

给定一个包含正整数和负整数的列表，我们必须找出列表中符号(正或负)变化的次数。

```
Input: [-1, 2, 3, -4, 5, -6, 7, 8, -9, 10, -11, 12] 
Output:9
Explanation : 
Sign change from -1 to 2, ans = 1
Sign change from 3 to -4, ans = 2
Sign change from -4 to 5, ans = 3
Sign change from 5 to -6, ans = 4
Sign change from -6 to 7, ans = 5
Sign change from 8 to -9, ans = 6
Sign change from -9 to 10, ans = 7
Sign change from 10 to -11 ans = 8
Sign change from -11 to 12, ans = 9

Input: [-1, 2, 3, -4, 5, -11, 12]  
Output:5
Explanation :
Sign change from -1 to 2, ans = 1
Sign change from 3 to -4, ans = 2
Sign change from -4 to 5, ans = 3
Sign change from 5 to -11, ans = 4
Sign change from -11 to 12, ans = 5

```

让我们讨论执行这项任务的某些方式。

**方法#1:使用迭代**
使用迭代在列表中查找时间符号变化的次数。

```
# Python Code to find number of 
# time sign changes in the list.

# Input list Initialization
Input = [-1, 2, 3, -4, 5, -6, 7, 8, -9, 10, -11, 12] 

# Variable Initialization
prev = Input[0]
ans = 0

# Using Iteration
for elem in Input:
    if elem == 0:
        sign = -1
    else:
        sign = elem / abs(elem)

    if sign == -prev:
        ans = ans + 1
        prev = sign

# Printing answer
print(ans)
```

**输出:**

```
9
```

**方法 2:使用 Itertools 和 groupby**
这是使用 itertools 执行这一特定任务的另一种方式。

```
# Python Code to find number of 
# time sign changes in the list.

# Input list Initialization
Input = [-1, 2, 3, -4, 5, -6, 7, 8, -9, 10, -11, 12] 

# Importing
import itertools

# Using groupby
Output = len(list(itertools.groupby(Input, lambda Input: Input > 0)))

Output = Output -1

# Printing output
print(Output)
```

**输出:**

```
9
```

**方法三:使用 Zip**
在列表中查找时间标志变化次数最简洁易读的方法是使用 Zip。

```
# Python Code to find number of 
# time sign changes in the list.

# Using zip to check
def check(Input):
    Input = [-1 if not x else x for x in Input]
    # zip with leading 1, so that opening negative value is 
    # treated as sign change
    return sum((x ^ y)<0 for x, y in zip([1]+Input, Input))

# Input list Initialization
Input = [-1, 2, 3, -4, 5, -6, 7, 8, -9, 10, -11, 12] 
Output = check(Input)

Output = Output -1

# Printing output
print(Output)
```

**输出:**

```
9
```