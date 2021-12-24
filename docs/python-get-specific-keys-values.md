# Python |获取特定键的值

> 原文:[https://www . geesforgeks . org/python-get-specific-key-values/](https://www.geeksforgeeks.org/python-get-specific-keys-values/)

有时候，我们需要所有的值，但是很多时候，我们已经指定了我们需要其值列表的键。这是 web 开发中很常见的问题。让我们讨论一下解决这个问题的某些方法。

**方法#1:使用列表理解**
该任务可以使用列表理解来执行，列表理解被用作使用循环执行较长检查任务的较短方式。这提供了一个解决这个问题的线性方法。

```py
# Python3 code to demonstrate working of
# Get specific keys' values
# Using list comprehension

# initializing dictionary
test_dict = {'gfg' : 1, 'is' : 2, 'best' : 3}

# initializing keys
filt_keys = ['gfg', 'best']

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# Extract specific value list from dictionary
# Using list comprehension
res = [test_dict[key] for key in filt_keys]

# printing result
print("Filtered value list is : " +  str(res))
```

**Output :**

```py
The original dictionary is : {'is': 2, 'best': 3, 'gfg': 1}
Filtered value list is : [1, 3]

```