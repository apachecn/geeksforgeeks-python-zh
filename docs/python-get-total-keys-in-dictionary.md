# Python |获取字典中的总键数

> 原文:[https://www . geesforgeks . org/python-get-total-keys-in-dictionary/](https://www.geeksforgeeks.org/python-get-total-keys-in-dictionary/)

有时，在使用 Python 字典时，可能会遇到一个问题，即需要获得整个字典(包括嵌套字典)中存在的键的确切数量。让我们讨论执行这项任务的某些方法。

**方法#1:使用递归+ `items() + sum() + len()`**
这个任务可以使用上述函数的组合来执行。在这种情况下，我们检查一个嵌套是否是一个非字典，然后使用`items()`提取它的键，然后使用各自的函数对它的长度求和。

```py
# Python3 code to demonstrate working of
# Get total keys in dictionary
# Using recursion + items() + sum() + len()

# Utility function to perform task 
def total_keys(test_dict):
    return (0 if not isinstance(test_dict, dict) 
    else len(test_dict) + sum(total_keys(val) for val in test_dict.values()))

# Initialize dictionary
test_dict = { 'gfg' : { 'is'  : 1, 'best' : { 'for' : {'geeks' :4}}}}

# Printing original dictionary
print("The original dictionary is : " + str(test_dict))

# Using recursion + items() + sum() + len()
# Get total keys in dictionary
res = total_keys(test_dict)

# printing result 
print("Number of keys in dictionary is : " + str(res))
```

**Output :**

> 原始字典为:{ ' gfg ':{ ' best ':{ ' for ':{ ' geeks ':4 } }，' is': 1}}
> 字典中的键数为:5