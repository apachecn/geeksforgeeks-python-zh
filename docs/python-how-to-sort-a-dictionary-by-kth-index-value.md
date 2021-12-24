# Python–如何根据第 k 个索引值对字典进行排序

> 原文:[https://www . geeksforgeeks . org/python-如何按 kth-index-value 对字典进行排序/](https://www.geeksforgeeks.org/python-how-to-sort-a-dictionary-by-kth-index-value/)

在使用 Python 时，可能会遇到一个问题，即需要基于值列表的 Kth 索引对字典执行排序。这通常是在评分或网络开发的情况下。让我们讨论一种执行这项任务的方法。

> **输入** : test_dict = {'gfg' : [5，6，7]，' is' : [1，4，7]，' best' : [8，3，1]}，K = 2
> **输出** : [('best '，[8，3，1])，(' gfg '，[5，6，7])，(' is '，[1，4，7])]
> 
> **输入** : test_dict = {'gfg' : [5，6，7]，' is' : [1，4，7]，' best' : [8，3，1]}，K = 0
> **输出** : [('is '，[1，4，7])，(' gfg '，[5，6，7])，(' best '，[8，3，1])]

**方法:使用`sorted()`+λ**
以上功能的组合可以解决这个问题。在本例中，我们使用 sorted()执行排序，lambda 函数用于驱动 Kth 索引逻辑。

```py
# Python3 code to demonstrate working of 
# Sort Dictionary by Kth Index Value
# Using sorted() + lambda

# initializing dictionary
test_dict = {'gfg' : [5, 6, 7],
             'is' : [1, 4, 7],
             'best' : [8, 3, 1]}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# initializing K
K = 1

# Sort Dictionary by Kth Index Value
# Using sorted() + lambda
res = sorted(test_dict.items(), key = lambda key: key[1][K])

# printing result 
print("The sorted dictionary : " + str(res)) 
```

**Output :**

```py
The original dictionary is : {'gfg': [5, 6, 7], 'is': [1, 4, 7], 'best': [8, 3, 1]}
The sorted dictionary : [('best', [8, 3, 1]), ('is', [1, 4, 7]), ('gfg', [5, 6, 7])]

```