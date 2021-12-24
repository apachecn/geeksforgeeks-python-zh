# Python–提取唯一值字典值

> 原文:[https://www . geeksforgeeks . org/python-extract-unique-values-dictionary-values/](https://www.geeksforgeeks.org/python-extract-unique-values-dictionary-values/)

有时，在处理数据时，我们可能会遇到这样的问题，即需要从字典值列表中仅提取唯一值。这在许多领域都有应用，比如 web 开发。让我们讨论执行这项任务的某些方法。

**方法#1:使用`sorted() + set comprehension + values()`**
上述功能的组合可用于执行该任务。在这种情况下，我们使用 values()提取所有值，并使用集合理解来获取列表中编译的唯一值。

```
# Python3 code to demonstrate working of 
# Extract Unique values dictionary values
# Using set comprehension + values() + sorted()

# initializing dictionary
test_dict = {'gfg' : [5, 6, 7, 8],
             'is' : [10, 11, 7, 5],
             'best' : [6, 12, 10, 8],
             'for' : [1, 2, 5]}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# Extract Unique values dictionary values
# Using set comprehension + values() + sorted()
res = list(sorted({ele for val in test_dict.values() for ele in val}))

# printing result 
print("The unique values list is : " + str(res)) 
```

**Output :**

> 原始字典为:{'gfg': [5，6，7，8]，' best': [6，12，10，8]，' is': [10，11，7，5]，' for': [1，2，5]}
> 唯一值列表为:[1，2，5，6，7，8，10，11，12]