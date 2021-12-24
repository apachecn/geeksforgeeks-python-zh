# Python–字典中自定义元组键求和

> 原文:[https://www . geesforgeks . org/python-custom-tuple-key-summary-in-dictionary/](https://www.geeksforgeeks.org/python-custom-tuple-key-summation-in-dictionary/)

有时，在使用 Python 字典时，我们会遇到一个问题，即需要对字典元组键的特定索引上的某些键的值进行分组求和。这个问题是非常定制的，但是可以在围绕数据处理的领域中应用。让我们讨论执行这项任务的某些方法。

> **输入** :
> test_dict = {('a '，' b'): 14，(' c '，' a'): 16，(' a '，' c'): 67}
> K = 'c '，idx = 1
> T5】输出 : 16
> 
> **输入** :
> test_dict = {('a '，' b'): 14，(' c '，' a'): 16，(' a '，' c'): 67}
> K = 'c '，idx = 2
> T5】输出 : 67

**方法#1:使用`sum()` +生成器表达式**
以上功能的组合可以解决这个问题。在本文中，我们使用 sum()执行求和，并使用生成器表达式执行过滤任务。

```py
# Python3 code to demonstrate working of 
# Custom Tuple Key Summation in Dictionary
# Using sum() + generator expression

# initializing dictionary
test_dict = {('a', 'b'): 14, ('c', 'a'): 16, ('a', 'c'): 67, ('b', 'a'): 17}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# initializing K 
K = 'a'

# initializing index
idx = 1

# Custom Tuple Key Summation in Dictionary
# Using sum() + generator expression
res = sum(val for key, val in test_dict.items() if key[idx - 1] == K)

# printing result 
print("The grouped summation : " + str(res)) 
```

**Output :**

```py
The original dictionary is : {('a', 'b'): 14, ('c', 'a'): 16, ('a', 'c'): 67, ('b', 'a'): 17}
The grouped summation : 81

```

**方法 2:使用`sum() + map() + lambda`**
以上功能的组合可以用来解决这个问题。在这种情况下，我们使用 sum()执行求和任务，而 map() + lambda 用于执行检查条件的任务。

```py
# Python3 code to demonstrate working of 
# Custom Tuple Key Summation in Dictionary
# Using sum() + map() + lambda

# initializing dictionary
test_dict = {('a', 'b'): 14, ('c', 'a'): 16, ('a', 'c'): 67, ('b', 'a'): 17}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# initializing K 
K = 'a'

# initializing index
idx = 1

# Custom Tuple Key Summation in Dictionary
# Using sum() + map() + lambda
res = sum(map(lambda sub: sub[1], filter(lambda ele: ele[0][idx - 1] == K,
                                                     test_dict.items())))

# printing result 
print("The grouped summation : " + str(res)) 
```

**Output :**

```py
The original dictionary is : {('a', 'b'): 14, ('c', 'a'): 16, ('a', 'c'): 67, ('b', 'a'): 17}
The grouped summation : 81

```