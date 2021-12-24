# Python |替换字符添加

> 原文:[https://www . geesforgeks . org/python-alternate-character-addition/](https://www.geeksforgeeks.org/python-alternate-character-addition/)

有时，在使用 Python 时，我们会遇到一个问题，即需要在 String 中的每个字符后添加一个字符。这种问题可以在许多日常编程领域中得到应用。让我们讨论执行这项任务的某些方法。
**方法#1:使用循环**
这是可以执行这个任务的蛮力方式。在这种情况下，我们迭代每个元素并插入所需的字符。我们抹去最后一个流浪角色。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Alternate character addition
# Using loop

# initializing string
test_str = "geeksforgeeks"

# printing original string
print("The original string is : " + test_str)

# initializing K
K = '*'

# Alternate character addition
# Using loop
res = ''
for ele in test_str:
    res += ele + K
res = res[:-1]

# printing result
print("String after character addition : " + str(res))
```

**Output : **

```
The original string is : geeksforgeeks
String after character addition : g*e*e*k*s*f*o*r*g*e*e*k*s
```

**方法 2:使用 join()**
这是执行此任务最简单、优雅且推荐的方法。在这种情况下，我们只使用一行来执行这个任务。join()用于执行它。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Alternate character addition
# Using join()

# initializing string
test_str = "geeksforgeeks"

# printing original string
print("The original string is : " + test_str)

# initializing K
K = '*'

# Alternate character addition
# Using join()
res = K.join(test_str)

# printing result
print("String after character addition : " + str(res))
```

**Output : **

```
The original string is : geeksforgeeks
String after character addition : g*e*e*k*s*f*o*r*g*e*e*k*s
```