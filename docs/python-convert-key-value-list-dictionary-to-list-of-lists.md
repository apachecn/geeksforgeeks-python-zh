# Python–将键值列表字典转换为列表列表

> 原文:[https://www . geesforgeks . org/python-convert-key-value-list-dictionary-to-list-list/](https://www.geeksforgeeks.org/python-convert-key-value-list-dictionary-to-list-of-lists/)

有时，在使用 Python 字典时，我们可能会遇到一个问题，需要将字典的键值对展平为列表，并转换为列表的列表。这可以在我们拥有数据的领域中得到应用。让我们讨论执行这项任务的某些方法。

**方法#1:使用 loop + `items()`**
这种蛮力的方式我们可以执行这个任务。在这种情况下，我们循环遍历所有对，并使用 items()提取列表值元素，并在新列表中呈现。

```py
# Python3 code to demonstrate working of 
# Convert Key-Value list Dictionary to Lists of List
# Using loop + items()

# initializing Dictionary
test_dict = {'gfg' : [1, 3, 4], 'is' : [7, 6], 'best' : [4, 5]}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# Convert Key-Value list Dictionary to Lists of List
# Using loop + items()
res = []
for key, val in test_dict.items():
    res.append([key] + val)

# printing result 
print("The converted list is : " + str(res)) 
```

**Output :**

> 原始字典为:{'gfg': [1，3，4]，' is': [7，6]，' best': [4，5]}
> 转换后的列表为:[['gfg '，1，3，4]，['is '，7，6]，['best '，4，5]]