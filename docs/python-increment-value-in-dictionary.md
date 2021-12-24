# Python |字典中的增量值

> 原文:[https://www . geesforgeks . org/python-increment-value-in-dictionary/](https://www.geeksforgeeks.org/python-increment-value-in-dictionary/)

有时候，在使用字典时，我们可能会遇到一个用例，在这个用例中，我们需要增加字典中某个特定键的值。这看起来是一个非常直接的问题，但是当不知道某个键的存在时，catch 就会出现，因此有时会变成一个两步的过程。让我们讨论执行这项任务的某些方法。

**方法#1:使用`get()`**
get 函数可以用 0 初始化一个不存在的键，然后增量是可能的。这样可以避免密钥不存在的问题。

```
# Python3 code to demonstrate working of
# Increment value in dictionary
# Using get()

# Initialize dictionary
test_dict = {'gfg' : 1, 'is' : 2, 'for' : 4, 'CS' : 5}

# printing original dictionary
print("The original dictionary : " +  str(test_dict))

# Using get()
# Increment value in dictionary
test_dict['best'] = test_dict.get('best', 0) + 3

# printing result 
print("Dictionary after the increment of key : " + str(test_dict))
```

**Output :**

> 原始字典:{'is': 2，' CS': 5，' for': 4，' gfg': 1}
> 索引键递增后的字典:{'is': 2，' CS': 5，' for': 4，' best': 3，' gfg': 1}