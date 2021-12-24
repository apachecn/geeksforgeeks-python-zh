# Python |将关节浮点字符串转换为数字

> 原文:[https://www . geesforgeks . org/python-convert-joint-float-string-to-numbers/](https://www.geeksforgeeks.org/python-convert-joint-float-string-to-numbers/)

有时，在使用遗留语言时，我们会遇到某些问题。一个这样的例子是使用 FORTRAN，它可以给出文本输出(没有空格，这是必需的)‘12 . 4567 . 23’。在这种情况下，实际上有两个独立的浮点数字，但连接在一起。我们可能会遇到需要将它们分开的问题。让我们讨论执行这项任务的某些方法。
**方法#1:使用 loop + float()**
这是可以执行此任务的蛮力方法。在这种情况下，我们对每个元素进行迭代，并分成 4 个块，跳到每第 5 个元素，执行拆分并存储在列表中。从字符串到浮点的对话是使用 float()完成的。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Convert Joint Float string to Numbers
# Using loop + float()

# initializing string
test_str = "45.6778.4524.45"

# printing original string
print("The original string is : " + test_str)

# Convert Joint Float string to Numbers
# Using loop + float()
res = []
for idx in range(0, len(test_str), 5):
    res.append(float(test_str[idx : idx + 5]))

# printing result
print("The float list is : " + str(res))
```

**Output : **

```
The original string is : 45.6778.4524.45
The float list is : [45.67, 78.45, 24.45]
```

**方法 2:使用列表理解+ float()**
这是解决这个问题的速记方式。这类似于上面的功能。不同的是，我们使用列表理解在单行中执行所有循环任务。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Convert Joint Float string to Numbers
# Using list comprehension + float()

# initializing string
test_str = "45.6778.4524.45"

# printing original string
print("The original string is : " + test_str)

# Convert Joint Float string to Numbers
# Using list comprehension + float()
res = [float(test_str[idx : idx + 5]) for idx in range(0, len(test_str), 5)]

# printing result
print("The float list is : " + str(res))
```

**Output : **

```
The original string is : 45.6778.4524.45
The float list is : [45.67, 78.45, 24.45]
```