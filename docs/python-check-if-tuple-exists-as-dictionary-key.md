# Python |检查元组是否作为字典关键字存在

> 原文:[https://www . geesforgeks . org/python-check-if-tuple-exists-as-dictionary-key/](https://www.geeksforgeeks.org/python-check-if-tuple-exists-as-dictionary-key/)

有时，在使用字典时，它的键有可能是元组的形式。这可能是某些 web 开发领域的子问题。让我们讨论一下解决这个问题的某些方法。

**方法#1:使用`in operator`**
这是执行这一特定任务最推荐和皮托尼克的方式。它检查特定的元组，并在出现元组时返回真，否则返回假。

```
# Python3 code to demonstrate working of
# Check if tuple exists as dictionary key
# using in operator

# initialize dictionary
test_dict = { (3, 4) : 'gfg', 6 : 'is', (9, 1) : 'best'}

# printing original dictionary
print("The original dictionary : " + str(test_dict))

# initialize target tuple 
tar_tup = (3, 4)

# Check if tuple exists as dictionary key
# using in operator
res = tar_tup in test_dict

# printing result
print("Does tuple exists as dictionary key ? : " + str(res))
```

**Output :**

```
The original dictionary : {(3, 4): 'gfg', (9, 1): 'best', 6: 'is'}
Does tuple exists as dictionary key ? : True

```