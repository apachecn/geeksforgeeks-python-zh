# Python–将值转换为比例

> 原文:[https://www . geesforgeks . org/python-convert-values-in-partition/](https://www.geeksforgeeks.org/python-convert-values-into-proportions/)

有时，在使用 Python 字典时，我们可能会遇到这样的问题，即需要将值转换为相对于总数的比例。这可以在数据科学和机器学习领域得到应用。让我们讨论执行这项任务的某些方法。

**方法#1:使用`sum()` +循环**
以上功能的组合可以用来解决这个问题。在本文中，我们使用 sum()执行求和的任务。除法的任务是在一个循环中用每个值的和进行除法来完成的。

```py
# Python3 code to demonstrate working of 
# Convert Values into proportions
# Using sum() + loop

# initializing dictionary
test_dict = { 'gfg' : 10, 'is' : 15, 'best' : 20 }

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# Convert Values into proportions
# Using sum() + loop
temp = sum(test_dict.values())
for key, val in test_dict.items():
    test_dict[key] = val / temp

# printing result 
print("The proportions divided values : " + str(test_dict)) 
```

**Output :**

> 原始字典为:{'is': 15，' best': 20，' gfg': 10}
> 比例除数值:{'is': 0.33333333333333，' best': 0.4444444444444，' gfg ':0.222222222222 }