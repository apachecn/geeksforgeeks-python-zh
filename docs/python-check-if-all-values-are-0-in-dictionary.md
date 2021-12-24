# Python |检查字典中所有值是否为 0

> 原文:[https://www . geesforgeks . org/python-check-如果所有值都是字典中的 0/](https://www.geeksforgeeks.org/python-check-if-all-values-are-0-in-dictionary/)

在使用字典时，我们可能会遇到一个问题，即我们需要确保字典中的所有值都为 0。在检查启动状态或检查可能发生的错误/操作时，可能会出现这种问题。让我们讨论执行这项任务的某些方法。

**方法一:使用`all()` +字典理解**
以上功能的组合可以用来执行以下任务。all 函数检查每个键，字典理解检查 0 值。

```
# Python3 code to demonstrate working of
# Check if all values are 0 in dictionary
# Using all() + dictionary comprehension

# Initialize dictionary
test_dict = {'gfg' : 0, 'is' : 0, 'best' : 0}

# Printing original dictionary 
print("The original dictionary is : " + str(test_dict))

# using all() + dictionary comprehension
# Check if all values are 0 in dictionary
res = all(x == 0 for x in test_dict.values())

# printing result 
print("Does all keys have 0 value ? : " + str(res))
```

**Output :**

```
The original dictionary is : {'gfg': 0, 'is': 0, 'best': 0}
Does all keys have 0 value ? : True

```