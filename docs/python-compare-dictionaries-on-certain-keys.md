# Python–比较特定键上的字典

> 原文:[https://www . geesforgeks . org/python-compare-dictionary-on-keys/](https://www.geeksforgeeks.org/python-compare-dictionaries-on-certain-keys/)

有时，在使用 Python 字典时，我们可能会遇到一个问题，即我们需要在选定键的基础上比较字典是否相等。这种问题很常见，在许多领域都有应用。让我们讨论执行这项任务的某些方法。

**方法#1:使用循环**
这是可以执行该任务的蛮力方式。在本文中，我们对字典进行迭代，并使用所选键中的相等运算符手动测试键的相等性。

```
# Python3 code to demonstrate working of 
# Compare Dictionaries on certain Keys
# Using loop

# initializing dictionaries
test_dict1 = {'gfg' : 1, 'is' : 2, 'best' : 3, 'for' : 4, 'geeks' : 5}
test_dict2 = {'gfg' : 2, 'is' : 3, 'best' : 3, 'for' : 7, 'geeks' : 5}

# printing original dictionaries
print("The original dictionary 1 : " + str(test_dict1))
print("The original dictionary 2 : " + str(test_dict2))

# initializing compare keys 
comp_keys = ['best', 'geeks']

# Compare Dictionaries on certain Keys
# Using loop
res = True
for key in comp_keys:
    if test_dict1.get(key) != test_dict2.get(key):
        res = False
        break 

# printing result 
print("Are dictionary equal : " + str(res)) 
```

**Output :**

> 原词典 1 : {“极客”:5，“gfg”:1，“is”:2，“for”:4，“best”:3 }
> 原词典 2 : {“极客”:5，“gfg”:2，“is”:3，“for”:7，“best”:3 }
> 是否词典相等:True