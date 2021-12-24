# Python–提取包含嵌套键的选择性键的值

> 原文:[https://www . geesforgeks . org/python-extract-selective-key-values-include-nested-keys/](https://www.geeksforgeeks.org/python-extract-selective-keys-values-including-nested-keys/)

有时，在使用 Python 字典时，我们可能会遇到一个问题，需要提取选择性键的值。这个问题之前已经解决了，但是有时候，我们可以有多个嵌套，某些键可能会出现在内部记录中。这个问题适用于所有提取键值的嵌套。让我们讨论一下解决这个任务的某些方法。

> **输入** :
> test_dict = {'gfg': { '极客':{'best' : 3} }
> key _ list =[' best '，'极客']
> T5】输出 : { '极客':{ ' best' : 3}，' best ':3 }
> 
> **输入**:
> test _ dict = { ' gfg ':{ ' geek ':{ ' good ':3 } }
> key _ list =[' best '，' geek ']
> T5】输出 : {}

**方法:使用递归+循环+产量**
以上功能的组合可以用来解决这个问题。在本文中，我们使用条件语句执行检查键的任务，并使用递归检查嵌套。yield 运算符用于在发生时动态返回 s signation 的密钥。

```py
# Python3 code to demonstrate working of 
# Extract selective keys' values [ Including Nested Keys ]
# Using recursion + loop + yield

def get_vals(test_dict, key_list):
   for i, j in test_dict.items():
     if i in key_list:
        yield (i, j)
     yield from [] if not isinstance(j, dict) else get_vals(j, key_list)

# initializing dictionary
test_dict = {'gfg': {'is': {'best' : 3}}, 'for': {'all' : 4}, 'geeks': 5}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# initializing keys list 
key_list = ['best', 'geeks']

# Extract selective keys' values [ Including Nested Keys ]
# Using recursion + loop + yield
res = dict(get_vals(test_dict, key_list))

# printing result 
print("The extracted values : " + str(res)) 
```

**Output :**

```py
The original dictionary is : {'gfg': {'is': {'best': 3}}, 'for': {'all': 4}, 'geeks': 5}
The extracted values : {'best': 3, 'geeks': 5}

```