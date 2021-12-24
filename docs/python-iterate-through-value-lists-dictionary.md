# Python |遍历值列表字典

> 原文:[https://www . geesforgeks . org/python-iterate-through-value-list-dictionary/](https://www.geeksforgeeks.org/python-iterate-through-value-lists-dictionary/)

在使用字典时，我们可能会遇到这样的情况:我们需要遍历字典键中的列表。这种问题可能发生在 web 开发领域。让我们讨论一下解决这个问题的某些方法。

**方法#1:使用列表理解**
列表理解可以用来执行这个特定的任务。这只是传统嵌套循环的简写。我们迭代每个键的列表并存储结果。

```
# Python3 code to demonstrate working of
# Iterating through value lists dictionary
# Using list comprehension

# Initialize dictionary
test_dict = {'gfg' : [1, 2], 'is' : [4, 5], 'best' : [7, 8]}

# printing original dictionary
print("The original dictionary : " +  str(test_dict))

# Using list comprehension
# Iterating through value lists dictionary
res = [[i for i in test_dict[x]] for x in test_dict.keys()]

# printing result 
print("The list values of keys are : " + str(res))
```

**Output :**

> 原始字典:{'best': [7，8]，' is': [4，5]，' gfg': [1，2]}
> 键的列表值为:[[7，8]，[4，5]，[1，2]]