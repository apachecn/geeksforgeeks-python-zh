# Python–连接矩阵中的字符串行

> 原文:[https://www . geesforgeks . org/python-concatenate-string-row-in-matrix/](https://www.geeksforgeeks.org/python-concatenate-string-rows-in-matrix/)

矩阵问题在竞争程序设计和数据科学领域都很常见。我们可能面临的一个问题是在大小不均匀的矩阵中寻找矩阵行的连接。让我们讨论一下解决这个问题的某些方法。

**方法一:使用 `join()` +列表理解**
上述功能的组合可以帮助在一行中获得这个特定问题的解决方案，因此非常有用。连接函数计算子列表的连接，并使用列表理解将所有这些绑定在一起。

```py
# Python3 code to demonstrate
# Row String Concatenation Matrix
# using join() + list comprehension

# initializing list
test_list = [['gfg', ' is', ' best'], ['Computer', ' Science'], ['GeeksforGeeks']]

# printing original list
print("The original list : " + str(test_list))

# using join() + list comprehension
# Row String Concatenation Matrix
res = [''.join(idx for idx in sub) for sub in test_list ]

# print result
print("The row concatenation in matrix : " + str(res))
```

**Output :**

```py
The original list : [['gfg', ' is', ' best'], ['Computer', ' Science'], ['GeeksforGeeks']]
The row concatenation in matrix : ['gfg is best', 'Computer Science', 'GeeksforGeeks']

```