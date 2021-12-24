# Python |检查非无值是否连续

> 原文:[https://www . geesforgeks . org/python-检查非无值是否连续/](https://www.geeksforgeeks.org/python-check-if-non-none-values-are-contiguous/)

有时，在使用 Python 列表时，我们可能会遇到一个问题，即我们需要找到是否所有的值都有效(非无)。这在日常编程中有很多应用。让我们讨论一种可以执行这项任务的方法。

**方法:使用迭代器+ `all() + any()`**
以上功能的组合可以用来执行这个特定的任务。在这种情况下，我们使用初始 all()过滤前导无值，然后使用 any()检查单个有效值子列表，然后检查所有必需的无值。如果以上任何一项返回 false。非无值不连续。

```py
# Python3 code to demonstrate working of
# Check if Non-None values are contiguous
# Using iterator + all() + any()

# helper function 
def check_cont(test_list):
    test_list = iter(test_list)
    all(x is None for x in test_list)        
    any(x is None for x in test_list)      
    return all(x is None for x in test_list)

# initializing list 
test_list = [None, None, 'Gfg', 'is', 'Good', None, None, None]

# printing list 
print("The original list : " + str(test_list))

# Check if Non-None values are contiguous
# Using iterator + all() + any()
res = check_cont(test_list)

# Printing result
print("Are non-none values contiguous ? : " + str(res))
```

**Output :**

```py

The original list : [None, None, 'Gfg', 'is', 'Good', None, None, None]
Are non-none values contiguous ? : True

```