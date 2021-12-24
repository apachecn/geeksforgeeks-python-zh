# Python–将键值列表转换为平面字典

> 原文:[https://www . geesforgeks . org/python-convert-key-values-list-to-flat-dictionary/](https://www.geeksforgeeks.org/python-convert-key-values-list-to-flat-dictionary/)

有时，在使用 Python 字典时，我们可能会遇到一个问题，即我们需要展平将相等的索引元素配对在一起的键值对字典。这可以在网络开发和数据科学领域中得到应用。让我们讨论执行这项任务的特定方式。

**方法:`zip() + dict()`**
以上功能的组合可以用来实现所需的任务。在本例中，我们使用 zip()执行配对，dict()用于将 zip()返回的元组数据转换为字典格式。

```
# Python3 code to demonstrate working of 
# Convert key-values list to flat dictionary
# Using dict() + zip()
from itertools import product

# initializing dictionary
test_dict = {'month' : [1, 2, 3],
             'name' : ['Jan', 'Feb', 'March']}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# Convert key-values list to flat dictionary
# Using dict() + zip()
res = dict(zip(test_dict['month'], test_dict['name']))

# printing result 
print("Flattened dictionary : " + str(res)) 
```

**Output :**

> 原词典为:{'name': ['Jan '，' Feb '，' March']，' month': [1，2，3]}
> 拼合词典:{1: 'Jan '，2: 'Feb '，3: 'March'}