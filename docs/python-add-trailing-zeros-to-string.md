# Python |在字符串中添加尾随零

> 原文:[https://www . geesforgeks . org/python-add-training-zero to-string/](https://www.geeksforgeeks.org/python-add-trailing-zeros-to-string/)

有时，我们希望以一种可能需要在字符串末尾添加额外零的方式来操作字符串；在填充缺失位或任何其他特定要求的情况下。这类问题的解决方法总是很方便，如果你有这方面的知识就很好。让我们讨论一下解决这个问题的某些方法。

**方法#1:使用`ljust()`**

这个任务可以使用简单的内置字符串函数*和*来执行，其中我们只需要传递所需的零的数量和元素到右边的填充，在这种情况下是零。

```py
# Python3 code to demonstrate
# adding trailing zeros
# using ljust()

# initializing string 
test_string = 'GFG'

# printing original string 
print("The original string : " + str(test_string))

# No. of zeros required
N = 4

# using ljust()
# adding trailing zero
res = test_string.ljust(N + len(test_string), '0')

# print result
print("The string after adding trailing zeros : " + str(res))
```

**Output :**

```py
The original string : GFG
The string after adding trailing zeros : GFG0000

```

**方法 2:使用`format()`**

使用 format 函数进行字符串格式化可以很容易地执行这个任务，我们只需要提到元素总数、需要填充的元素以及填充的方向，在这种情况下是正确的。

```py
# Python3 code to demonstrate
# adding trailing zeros
# using format()

# initializing string 
test_string = 'GFG'

# printing original string 
print("The original string : " + str(test_string))

# No. of zeros required
N = 4

# using format()
# adding trailing zero
# N for number of elememts, '0' for Zero, and '<' for trailing
temp = '{:<07}'
res = temp.format(test_string)

# print result
print("The string after adding trailing zeros : " + str(res))
```

**Output :**

```py
The original string : GFG
The string after adding trailing zeros : GFG0000

```