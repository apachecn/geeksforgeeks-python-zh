# Python–在字典中获取下一个键

> 原文:[https://www . geesforgeks . org/python-get-next-key-in-dictionary/](https://www.geeksforgeeks.org/python-get-next-key-in-dictionary/)

有时，在使用 Python 字典时，我们可能会遇到需要按照字典顺序提取下一个键的问题。这可以从 Python 3.6 开始应用，因为字典是有序的。让我们讨论执行这项任务的某些方法。

**方法#1:使用 `index()` +循环**
上述功能的组合可用于执行该任务。在这种情况下，我们执行字典元素到列表的转换。然后使用 index()检查索引，并追加索引计数以获取下一项。

```py
# Python3 code to demonstrate working of 
# Get next key in Dictionary
# Using index() + loop

# initializing dictionary
test_dict = {'gfg' : 1, 'is' : 2, 'best' : 3}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# initializing key
test_key = 'is'

# Get next key in Dictionary
# Using index() + loop
temp = list(test_dict)
try:
    res = temp[temp.index(test_key) + 1]
except (ValueError, IndexError):
    res = None

# printing result 
print("The next key is : " + str(res)) 
```

**Output :**

```py
The original dictionary is : {'gfg': 1, 'best': 3, 'is': 2}
The next key is : best

```