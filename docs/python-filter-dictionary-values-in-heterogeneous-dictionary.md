# Python–过滤异构字典中的字典值

> 原文:[https://www . geesforgeks . org/python-filter-dictionary-values-in-异类-dictionary/](https://www.geeksforgeeks.org/python-filter-dictionary-values-in-heterogeneous-dictionary/)

有时，在使用 Python 字典时，我们可能会遇到一个问题，即我们需要根据特定类型上的特定条件过滤掉某些值，例如所有小于 k 的值。当字典值可能是异构的时，这个任务变得复杂。这种问题可以应用于许多领域。让我们讨论执行这项任务的某些方法。

> **输入** : test_dict = {'Gfg' : 10，' for ':'极客' }
> **输出** : {'Gfg': 10，' for ':'极客' }
> 
> **输入** : test_dict = {'Gfg ':'极客' }
> **输出** : {'Gfg ':'极客' }

**方法#1:使用 type() +字典理解**
以上功能的组合可以用来执行这个任务。在本文中，我们使用 type()检查整型，并在字典理解中过滤数据。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Filter dictionary values in heterogeneous dictionary
# Using type() + dictionary comprehension

# initializing dictionary
test_dict = {'Gfg' : 4, 'is' : 2, 'best' : 3, 'for' : 'geeks'}

# printing original dictionary
print("The original dictionary : " + str(test_dict))

# initializing K 
K = 3

# Filter dictionary values in heterogeneous dictionary
# Using type() + dictionary comprehension
res = {key : val for key, val in test_dict.items()
                   if type(val) != int or val > K}

# printing result 
print("Values greater than K : " + str(res)) 
```

**Output : **

```py
The original dictionary : {'Gfg': 4, 'for': 'geeks', 'is': 2, 'best': 3}
Values greater than K : {'Gfg': 4, 'for': 'geeks'}
```

**方法 2:使用 isinstance() +字典理解**
以上函数的组合也可以用来解决这个问题。在这种情况下，我们执行类似于上面的任务，但不同的是，类型测试是由 isintance()而不是 type()完成的。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Filter dictionary values in heterogeneous dictionary
# Using isinstance() + dictionary comprehension

# initializing dictionary
test_dict = {'Gfg' : 4, 'is' : 2, 'best' : 3, 'for' : 'geeks'}

# printing original dictionary
print("The original dictionary : " + str(test_dict))

# initializing K 
K = 3

# Filter dictionary values in heterogeneous dictionary
# Using isinstance() + dictionary comprehension
res = {key : val for key, val in test_dict.items() 
           if not isinstance(val, int) or val > K}

# printing result 
print("Values greater than K : " + str(res)) 
```

**Output : **

```py
The original dictionary : {'Gfg': 4, 'for': 'geeks', 'is': 2, 'best': 3}
Values greater than K : {'Gfg': 4, 'for': 'geeks'}
```