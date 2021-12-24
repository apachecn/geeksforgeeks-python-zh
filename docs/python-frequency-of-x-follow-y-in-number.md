# Python–数字中 x 跟随 y 的频率

> 原文:[https://www . geesforgeks . org/python-of-x-follow-y-in-number/](https://www.geeksforgeeks.org/python-frequency-of-x-follow-y-in-number/)

有时候，在 Python 中处理数字时，我们可能会遇到一个问题，我们需要得到一个数字跟随另一个数字的次数。这可以应用于许多领域，如日常编程和其他领域。让我们讨论执行这项任务的某些方法。

**方法#1:使用循环**
这是我们执行这个任务的蛮力方式。在这种情况下，我们遍历列表，不断检查结果的前一个和当前数字，并不断增加计数器。

```
# Python3 code to demonstrate working of
# Frequency of x follow y in Number
# using loop

def count_occ(num, next, prev):
    num = str(num)
    prev_chr = ""
    count = 0
    for chr in num:
        if chr == next and prev_chr == prev:
            count += 1
        prev_chr = chr
    return count

# initialize Number
test_num = 12457454

# printing original number
print("The original number : " + str(test_num))

# initialize i, j 
i, j = '4', '5'

# Frequency of x follow y in Number
# using loop
res = count_occ(test_num, j, i)

# printing result
print("The count of x preceding y : " + str(res))
```

**Output :**

```
The original number : 12457454
The count of x preceding y : 2

```