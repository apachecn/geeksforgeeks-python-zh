# Python–检查字典值列表中的键

> 原文:[https://www . geesforgeks . org/python-检查字典中的键-值-列表/](https://www.geeksforgeeks.org/python-check-for-key-in-dictionary-value-list/)

有时候，在处理数据时，我们可能会遇到一个问题:我们收到了一个字典，整个键都有字典列表作为值。在这种情况下，我们可能需要找到其中是否存在特定的键。让我们讨论执行这项任务的某些方法。

**方法#1:使用`any()`**
这是执行该任务的简单且最推荐的方式。在这种情况下，我们只需通过迭代检查值中的键。

```py
# Python3 code to demonstrate working of 
# Check for Key in Dictionary Value list
# Using any()

# initializing dictionary 
test_dict = {'Gfg' : [{'CS' : 5}, {'GATE' : 6}], 'for' : 2, 'CS' : 3} 

# printing original dictionary 
print("The original dictionary is : " + str(test_dict)) 

# initializing key
key = "GATE"

# Check for Key in Dictionary Value list
# Using any()
res = any(key in ele for ele in test_dict['Gfg'])

# printing result  
print("Is key present in nested dictionary list ?  : " + str(res)) 
```

**Output :**

```py
The original dictionary is : {'Gfg': [{'CS': 5}, {'GATE': 6}], 'for': 2, 'CS': 3}
Is key present in nested dictionary list ?  : True

```