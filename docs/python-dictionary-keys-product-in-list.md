# Python–字典键在列表中的产品

> 原文:[https://www . geesforgeks . org/python-dictionary-keys-in-product-list/](https://www.geeksforgeeks.org/python-dictionary-keys-product-in-list/)

使用 Python 字典可以进行许多操作，如分组和转换。但是有时候，我们也会遇到一个问题，那就是我们需要执行字典列表中键值的乘积。这个任务在日常编程中很常见。让我们讨论执行这项任务的某些方法。

**方法#1:使用循环+列表理解**
这是一种线性方法，用于执行获取特定键的乘积的任务，同时使用列表理解迭代字典列表中的相似键。

```
# Python3 code to demonstrate working of
# Dictionary Key's Product in list
# Using loop + list comprehension

def prod(val) :     
    res = 1         
    for ele in val:         
        res *= ele         
    return res

# Initialize list
test_list = [{'gfg' : 1, 'is' : 2, 'best' : 3}, {'gfg' : 7, 'is' : 3, 'best' : 5}, {'gfg' : 9, 'is' : 8, 'best' : 6}] 

# printing original list
print("The original list is : " + str(test_list))

# Dictionary Key's Product in list
# Using loop + list comprehension
res = prod(sub['gfg'] for sub in test_list)

# printing result
print("The product of particular key is : " + str(res))
```

**Output :**

```
The original list is : [{'is': 2, 'best': 3, 'gfg': 1}, {'is': 3, 'best': 5, 'gfg': 7}, {'is': 8, 'best': 6, 'gfg': 9}]
The product of particular key is : 63

```