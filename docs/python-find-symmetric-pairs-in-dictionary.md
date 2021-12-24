# Python |在字典中查找对称对

> 原文:[https://www . geesforgeks . org/python-find-symmetric-in-dictionary-pairs/](https://www.geeksforgeeks.org/python-find-symmetric-pairs-in-dictionary/)

有时，在使用 Python 字典时，可能会出现这样的问题，即希望获得对称的键值对，即具有相同值的键值对，而不管事实值是键还是值。让我们讨论执行这项任务的某些方法。

**方法#1:使用发电机+回路**

通过在运行时产生匹配键值对的值，这个任务可以在使用循环和生成器的强力方法中解决。

```
# Python3 code to demonstrate working of
# Find Symmetric Pairs in dictionary
# using generator + loop

# generator function to perform task
def find_sym_pairs(test_dict):
    for key in test_dict.keys():
        val = test_dict.get(key)

        if test_dict.get(val) == key:
            yield key, val
    return 

# Initializing dict
test_dict = {'a' : 1, 'b' : 2, 'c' : 3,  1 : 'a', 2 : 'b'}

# printing original dict 
print("The original dict is : " + str(test_dict))

# Find Symmetric Pairs in dictionary
# using generator + loop
res = []
for key, val in find_sym_pairs(test_dict):
    temp = (key, val)
    res.append(temp)

# printing result
print("The pairs of Symmetric values : " + str(res))
```

**Output :**

```
The original dict is : {'a': 1, 1: 'a', 'c': 3, 'b': 2, 2: 'b'}
The pairs of Symmetric values : [('a', 1), (1, 'a'), ('b', 2), (2, 'b')]

```

**方法 2:使用列表理解**

这项任务也可以作为一个单行任务来执行，使用列表理解作为执行基于循环的解决方案的一种简化方式。

```
# Python3 code to demonstrate working of
# Find Symmetric Pairs in dictionary
# Using list comprehension

# Initializing dict
test_dict = {'a' : 1, 'b' : 2, 'c' : 3,  1 : 'a', 2 : 'b'}

# printing original dict 
print("The original dict is : " + str(test_dict))

# Find Symmetric Pairs in dictionary
# Using list comprehension
temp = [(key, value) for key, value in test_dict.items()]
res = [(x, y) for (x, y) in temp if (y, x) in temp]

# printing result
print("The pairs of Symmetric values : " + str(res))
```

**Output :**

```
The original dict is : {'a': 1, 1: 'a', 'c': 3, 'b': 2, 2: 'b'}
The pairs of Symmetric values : [('a', 1), (1, 'a'), ('b', 2), (2, 'b')]

```