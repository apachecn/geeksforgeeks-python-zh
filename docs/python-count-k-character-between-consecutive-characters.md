# Python |计算连续字符之间的 K 个字符

> 原文:[https://www . geesforgeks . org/python-count-k-字符间连续字符/](https://www.geeksforgeeks.org/python-count-k-character-between-consecutive-characters/)

有时，在处理字符串时，我们可能会遇到一个问题，即我们需要检查连续字符之间每个字符的计数。这种类型的问题可以在日常和 web 开发领域中得到应用。让我们讨论执行这项任务的某些方法。

**方法#1:使用循环**
这是可以执行该任务的蛮力方式。在这种情况下，我们迭代列表，计算每个字符之间的 K 个字符。

```py
# Python3 code to demonstrate working of 
# Count K character between consecutive characters
# Using loop

# initializing string
test_str = "g...f..g.i..s....b..e....s...t"

# printing original string
print("The original string is : " + test_str)

# initializing K 
K = '.'

# Count K character between consecutive characters
# Using loop
count = 0
res = []
for ele in test_str:
    if ele == K:
        count += 1
    else:
        res.append(count)
        count = 0
res = res[1:]

# printing result 
print("List of character count : " + str(res)) 
```

**Output :**

```py
The original string is : g...f..g.i..s....b..e....s...t
List of character count : [3, 2, 1, 2, 4, 2, 4, 3]

```