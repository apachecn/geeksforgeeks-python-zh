# Python | K 字符拆分字符串

> 原文:[https://www . geesforgeks . org/python-k-character-split-string/](https://www.geeksforgeeks.org/python-k-character-split-string/)

在使用 python 字符串时，列表拆分的问题和应用程序是很常见的。在用例中，有些字符通常会被忽略。但是有时，我们可能不需要省略这些字符，而是将它们包含在我们的编程输出中。让我们讨论一下解决这个问题的某些方法。

**方法一:使用`split()` +列表理解**
这种操作可以使用拆分功能和列表理解进行。不省略字符的主要区别在于，我们特别在每个元素之后添加了我们在过程中可能省略的字符。

```py
# Python3 code to demonstrate
# K Character Split String
# using list comprehension + split()

# initializing string
test_string = "GfG_is_Best"

# printing original string
print("The original string : " + str(test_string))

# initializing K 
K = '_'

# using list comprehension + split()
# K Character Split String
res = [i for j in test_string.split(K) for i in (j, K)][:-1]

# print result
print("The list without omitting Character : " + str(res))
```

**Output :**

```py
The original string : GfG_is_Best
The list without omitting Character : ['GfG', '_', 'is', '_', 'Best']

```