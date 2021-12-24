# Python–在字典中追加多类型值

> 原文:[https://www . geesforgeks . org/python-append-multi-type-values-in-dictionary/](https://www.geeksforgeeks.org/python-append-multitype-values-in-dictionary/)

有时，在使用 Python 字典时，我们可能会遇到需要根据数据类型更新字典值的问题。这种类型的问题可以应用于包括数据在内的许多领域。让我们讨论一下解决这个问题的方法。

> **输入** : test_dict = {'gfg ':"，' is' : {}，' best' : []}
> **输出** : {'gfg': 'geeks '，' is': {'c': 7}，' best': [4，5]}
> 
> **输入**:test _ dict = { ' gfg ':' 123 '，' is' : {}，' best' : ['极客']}
> **输出**:{ ' gfg ':' 123 极客'，' is': {'c': 7}，' best': ['极客'，4，5]}

**方法:使用`isinstance() + update() + extend()`**
以上功能的组合可以用来执行此任务。在本例中，我们使用 isinstance()检查值的数据类型，并使用 update()执行字典更新，使用 extend()执行列表更新。

```
# Python3 code to demonstrate working of 
# Append Multitype Values in Dictionary
# Using isinstance() + update() + extend()

# helper_fnc
def update_dictionary(key, val, test_dict):

    if key not in test_dict:
        current_dict[key] = value 

    elif type(val) not in [str, list, dict]:
        raise ValueError("Invalid Data Type")

    elif isinstance(val, list):
        test_dict[key].extend(val)

    elif isinstance(val, dict):
        test_dict[key].update(val)

    else:
        test_dict[key] = test_dict[key] + val

    return test_dict

# initializing dictionary
test_dict = {'gfg' : "geekfor", 'is' : {'a' : 5, 'b' : 6}, 'best' : [1, 2, 3]}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# initializing dict, string and append
up_dict = {'c' : 7}
up_str = 'geeks'
up_list = [4, 5]

# Append Multitype Values in Dictionary
# Using isinstance() + update() + extend()
res = update_dictionary('gfg', up_str, test_dict)
res = update_dictionary('is', up_dict, res)
res = update_dictionary('best', up_list, res)

# printing result 
print("The update dictionary : " + str(res)) 
```

**Output :**

> 原始词典为:{'is': {'b': 6，' a': 5}，' best': [1，2，3]，' gfg': 'geekfor'}
> 更新词典:{'is': {'b': 6，' a': 5，' c': 7}，' best': [1，2，3，4，5]，' gfg ':' geek forgeks ' }