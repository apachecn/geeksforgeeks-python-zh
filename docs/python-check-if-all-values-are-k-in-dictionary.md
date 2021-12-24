# Python–检查字典中是否所有值都是 K

> 原文:[https://www . geesforgeks . org/python-check-如果所有值都是字典中的 k/](https://www.geeksforgeeks.org/python-check-if-all-values-are-k-in-dictionary/)

在使用字典时，我们可能会遇到一个问题，我们需要确保字典中的所有值都是 K。在检查启动状态或检查可能发生的错误/操作时，可能会出现这种问题。让我们讨论执行这项任务的某些方法。

**方法一:使用`all()` +字典理解**
以上功能的组合可以用来执行以下任务。 `all`功能检查每个键，字典理解检查 K 值。

```py
# Python3 code to demonstrate working of
# Test if all values are K in dictionary
# Using all() + dictionary comprehension

# Initialize dictionary
test_dict = {'gfg' : 8, 'is' : 8, 'best' : 8}

# Printing original dictionary 
print("The original dictionary is : " + str(test_dict))

# Initialize K 
K = 8

# using all() + dictionary comprehension
# Test if all values are K in dictionary
res = all(x == K for x in test_dict.values())

# printing result 
print("Does all keys have K value ? : " + str(res))
```

**Output :**

```py
The original dictionary is : {'gfg': 8, 'best': 8, 'is': 8}
Does all keys have K value ? : True

```