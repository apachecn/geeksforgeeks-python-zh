# Python–列表中的第一个偶数

> 原文:[https://www . geesforgeks . org/python-列表中的第一个偶数/](https://www.geeksforgeeks.org/python-first-even-number-in-list/)

有时，在处理列表时，我们会遇到一个问题，即我们需要提取第一次出现的某些数字。这也可以是偶数。这种问题在日常编程和竞争性编程中很常见。让我们讨论执行这项任务的某些方法。

**方法#1:使用循环**
这是可以执行该任务的蛮力方式。在这种情况下，我们循环遍历列表，当第一次出现偶数时，我们存储并打破循环。

```
# Python3 code to demonstrate 
# First Even Number in List
# using loop

# Initializing list
test_list = [43, 9, 6, 72, 8, 11]

# printing original list
print("The original list is : " + str(test_list))

# First Even Number in List
# using loop
res = None
for ele in test_list:
    if not ele % 2 :
        res = ele
        break

# printing result 
print ("The first even element in list is : " + str(res))
```

**Output :**

```
The original list is : [43, 9, 6, 72, 8, 11]
The first even element in list is : 6

```