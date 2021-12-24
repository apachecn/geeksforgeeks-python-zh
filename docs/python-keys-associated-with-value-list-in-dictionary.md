# Python–与字典中的值列表相关联的键

> 原文:[https://www . geesforgeks . org/python-key-associated-value-list-in-dictionary/](https://www.geeksforgeeks.org/python-keys-associated-with-value-list-in-dictionary/)

有时，在使用 Python 字典时，我们可能会遇到一个问题，即我们需要在值列表中找到特定值的键。这个问题很常见，可以应用于许多领域。让我们讨论执行这项任务的某些方法。

**方法#1:使用 loop + `items()`**
以上功能的组合可以用来解决这个问题。在这种情况下，我们使用 items()提取字典的所有元素，并使用循环来编译剩余的逻辑。

```
# Python3 code to demonstrate working of 
# Value's Key association
# Using loop + items()

# initializing dictionary
test_dict = {'gfg' : [4, 5], 'is' : [8], 'best' : [10, 12]}

# printing original dictionary
print("The original dictionary : " + str(test_dict))

# initializing value list 
val_list = [5, 10]

# Value's Key association
# Using loop + items()
temp = {}
for key, vals in test_dict.items():
    for val in vals:
        temp[val] = key
res = [temp[ele] for ele in val_list]

# printing result 
print("The keys mapped to " + str(val_list) + " are : " + str(res)) 
```

**Output:**

```
The original dictionary : {'gfg': [4, 5], 'best': [10, 12], 'is': [8]}
The keys mapped to [5, 10] are : ['gfg', 'best']

```