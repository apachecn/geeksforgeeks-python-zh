# Python–展平并移除字典中的键

> 原文:[https://www . geeksforgeeks . org/python-从字典中展平并移除键/](https://www.geeksforgeeks.org/python-flatten-and-remove-keys-from-dictionary/)

给定一个字典，执行某些字典键的展平和移除。

> **输入** : test_dict = {'a': 14、' b': 16、' c': {'d': {'e': 7}}，rem _ keys =[“c”、“a”、“d”]
> **输出** : {'b': 16、' e': 7}
> **解释**:所有“c”、“a”和“d”均已删除。
> **输入** : test_dict = {'a': 14、' b': 16、' c': {'d': {'e': 7}}，rem _ keys =[“c”、“d”、“e”]
> **输出** : {'a': 14、' b': 16}
> **说明**:所有“c”、“e”和“d”均已删除。

**方法:使用递归+ isinstance() +循环**

上述功能的组合可以用来解决这个问题。在这种情况下，我们使用 isinstance()检查字典作为嵌套字典的实例，并在每次内部字典中重复出现。循环用于迭代键。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Flatten and remove keys from Dictionary
# Using loop + recursion + isinstance()

# function to compute removal and flattening
def hlper_fnc(test_dict, rem_keys):
    if not isinstance(test_dict, dict):
        return test_dict
    res = {}

    for key, val in test_dict.items():
        rem = hlper_fnc(val, rem_keys)

        # performing removal
        if key not in rem_keys:
            res[key] = rem
        else:
            if isinstance(rem, dict):
                res.update(rem)
    return res

# initializing dictionary
test_dict = {'a': 14, 'b': 16, 'c': {'d': {'e': 7}}}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# initializing removal keys
rem_keys = ["c", "d"]

# calling helper function for task
res = hlper_fnc(test_dict, rem_keys)

# printing result
print("The removed and flattened dictionary : " + str(res))
```

**Output**The original dictionary is : {‘a’: 14, ‘b’: 16, ‘c’: {‘d’: {‘e’: 7}}} The removed and flattened dictionary : {‘a’: 14, ‘b’: 16, ‘e’: 7}