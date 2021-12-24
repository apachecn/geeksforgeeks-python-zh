# Python |统计混合列表中的字符串出现次数

> 原文:[https://www . geesforgeks . org/python-count-string-increments-in-mixed-list/](https://www.geeksforgeeks.org/python-count-string-occurrences-in-mixed-list/)

有时，在处理数据时，我们会遇到一个问题，需要检查特定数据类型的出现情况。在这种情况下，我们还会遇到一个需要检查字符串出现的问题。让我们讨论执行这项任务的某些方法。

**方法一:使用`isinstance()` +列表理解**
以上方法的组合可以用来执行此任务。在这种情况下，我们为字符串实例检查列表中的每个元素，并只使用字符串构建列表，然后返回它的长度。

```py
# Python3 code to demonstrate working of
# Check String occurrences in mixed list
# using isinstance() + list comprehension

# initialize list 
test_list = ['gfg', 1, True, 'is', 2, 'best']

# printing original list 
print("The original list : " + str(test_list))

# Check String occurrences in mixed list
# using isinstance() + list comprehension
res = len([val for val in test_list if isinstance(val, str)])

# printing result
print("Number of strings in list : " + str(res))
```

**Output :**

```py
The original list : ['gfg', 1, True, 'is', 2, 'best']
Number of strings in list : 3

```