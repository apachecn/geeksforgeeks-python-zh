# Python–将字符串转换为嵌套词典

> 原文:[https://www . geesforgeks . org/python-convert-string-to-nested-dictionary/](https://www.geeksforgeeks.org/python-convert-string-to-nested-dictionaries/)

有时，在使用字典时，我们会遇到一个问题，需要将一个字符串转换为嵌套字典，每个分隔符的出现都意味着一个新的嵌套。这是一个特殊的问题，但可能发生在数据域和日常编程中。让我们讨论一下完成这项任务的具体方法。

**方法:使用循环+递归**
这是执行这个任务的方式。在这种情况下，当我们遇到分隔符事件时，我们重复字典的嵌套。

```py
# Python3 code to demonstrate working of 
# Convert String to Nested Dictionaries
# Using loop

def helper_fnc(test_str, sep):
  if sep not in test_str:
    return test_str
  key, val = test_str.split(sep, 1)
  return {key: helper_fnc(val, sep)}

# initializing string
test_str = 'gfg_is_best_for_geeks'

# printing original string
print("The original string is : " + str(test_str))

# initializing separator
sep = '_'

# Convert String to Nested Dictionaries
# Using loop
res = helper_fnc(test_str, sep)

# printing result 
print("The nested dictionary is : " + str(res)) 
```

**Output :**

```py
The original string is : gfg_is_best_for_geeks
The nested dictionary is : {'gfg': {'is': {'best': {'for': 'geeks'}}}}

```