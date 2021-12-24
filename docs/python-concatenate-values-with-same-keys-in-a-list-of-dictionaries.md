# Python–在字典列表中用相同的键连接值

> 原文:[https://www . geeksforgeeks . org/python-在字典列表中用相同的键连接值/](https://www.geeksforgeeks.org/python-concatenate-values-with-same-keys-in-a-list-of-dictionaries/)

有时，在使用 Python 字典时，我们可能会遇到一个问题，即我们需要对字典列表中的所有键值列表进行串联。这是一个很常见的问题，在日常编程和 web 开发领域都有应用。让我们讨论执行这项任务的特定方式。

**方法:使用循环**
这个任务可以使用蛮力的方式来执行。在这种情况下，我们对所有字典进行迭代，并通过在关键字匹配中将一个列表元素添加到另一个来执行相似关键字的连接。

```py
# Python3 code to demonstrate working of 
# Concatenate Similar Key values
# Using loop

# initializing list
test_list = [{'gfg' : [1, 5, 6, 7], 'good' : [9, 6, 2, 10], 'CS' : [4, 5, 6]},
             {'gfg' : [5, 6, 7, 8], 'CS' : [5, 7, 10]},
             {'gfg' : [7, 5], 'best' : [5, 7]}]

# printing original list
print("The original list is : " + str(test_list))

# Concatenate Similar Key values
# Using loop
res = dict()
for dict in test_list:
    for list in dict:
        if list in res:
            res[list] += (dict[list])
        else:
            res[list] = dict[list]

# printing result 
print("The concatenated dictionary : " + str(res)) 
```

**Output :**

```py
The original list is : [{'CS': [4, 5, 6], 'good': [9, 6, 2, 10], 'gfg': [1, 5, 6, 7]}, {'CS': [5, 7, 10], 'gfg': [5, 6, 7, 8]}, {'best': [5, 7], 'gfg': [7, 5]}]
The concatenated dictionary : {'gfg': [1, 5, 6, 7, 5, 6, 7, 8, 7, 5], 'good': [9, 6, 2, 10], 'best': [5, 7], 'CS': [4, 5, 6, 5, 7, 10]}

```