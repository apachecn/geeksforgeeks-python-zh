# Python–在字典中查找特定后缀的键

> 原文:[https://www . geesforgeks . org/python-find-key-with-specific-后缀-in-dictionary/](https://www.geeksforgeeks.org/python-find-keys-with-specific-suffix-in-dictionary/)

有时，在使用字典时，我们可能会遇到一个问题，即我们需要找到对键有一些约束的字典项。一个这样的约束可以是键上的后缀匹配。让我们讨论执行这项任务的某些方法。

**方法#1:使用字典理解+ `endswith()`**
以上两种方法的组合可以用来执行这个特定的任务。在这种情况下，字典理解执行字典构建的基本任务，endswith()执行检查以特定后缀开始的键的实用任务。

```
# Python3 code to demonstrate working of
# Keys with specific suffix in Dictionary
# Using dictionary comprehension + endswith()

# Initialize dictionary
test_dict = {'all' : 4, 'geeks' : 5, 'are' : 8, 'freaks' : 10}

# printing original dictionary
print("The original dictionary : " + str(test_dict))

# Initialize suffix
test_suf = 'ks'

# Using dictionary comprehension + endswith()
# Keys with specific suffix in Dictionary
res = {key:val for key, val in test_dict.items() if key.endswith(test_suf)}

# printing result 
print("Filtered dictionary keys are : " + str(res))
```

**Output :**

```
The original dictionary : {'geeks': 5, 'freaks': 10, 'are': 8, 'all': 4}
Filtered dictionary keys are : {'geeks': 5, 'freaks': 10}

```