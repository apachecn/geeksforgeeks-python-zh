# Python |检查关键字在字典中是否有非无值

> 原文:[https://www . geesforgeks . org/python-check-if-key-has-non-non-value-in-dictionary/](https://www.geeksforgeeks.org/python-check-if-key-has-non-none-value-in-dictionary/)

有时候，在使用 Python 字典时，我们可能会遇到一个问题，我们需要找出字典的某个特定键是否有效，即它不是 False 或具有非 None 值。这种问题可能发生在机器学习领域。让我们讨论一下解决这个问题的某些方法。

**方法#1:使用 `if`**
这个任务可以简单的使用条件运算符`"if"`来解决。`if`语句自动检查任何语句的真实性，从而检查键的值。

```py
# Python3 code to demonstrate working of
# Check if key has Non-None value in dictionary
# Using if

# Initialize dictionary
test_dict = {'gfg' : None, 'is' : 4, 'for' : 2, 'CS' : 10}

# printing original dictionary
print("The original dictionary : " +  str(test_dict))

# Using if
# Check if key has Non-None value in dictionary
res = False
if test_dict['gfg']:
    res = True

# printing result 
print("Does gfg have a Non-None value? : " + str(res))
```

**Output :**

> 原始字典:{'gfg': None，' is': 4，' for': 2，' CS ':10 }
> gfg 是否有 Non-None 值？:假