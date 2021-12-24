# Python–关键列表汇总

> 原文:[https://www.geeksforgeeks.org/python-key-lists-summations/](https://www.geeksforgeeks.org/python-key-lists-summations/)

有时，在使用 Python 字典时，我们可能会遇到这样的问题，即需要用值中所有键的总和来替换键。这可以应用于包括数据计算在内的许多领域，例如机器学习。让我们讨论执行这项任务的某些方法。

**方法#1:使用`sum()` +循环**
这是可以执行该任务的方式之一。在这种情况下，我们使用 sum 执行求和，并使用 loop 以暴力方式对每个键进行迭代。

```py
# Python3 code to demonstrate working of 
# Key Values Summations
# Using sum() + loop

# initializing dictionary
test_dict = {'gfg' : [4, 6, 8], 'is' : [9, 8, 2], 'best' : [10, 3, 2]}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# Key Values Summations
# Using sum() + loop
for key, value in test_dict.items():
    test_dict[key] = sum(value)

# printing result 
print("The summation keys are : " + str(test_dict)) 
```

**Output :**

> 原始字典为:{'gfg': [4，6，8]，' is': [9，8，2]，' best': [10，3，2]}
> 求和键为:{'gfg': 18，' is': 19，' best': 15}