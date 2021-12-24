# Python–字典值字符串长度总和

> 原文:[https://www . geesforgeks . org/python-dictionary-values-string-length-summary/](https://www.geeksforgeeks.org/python-dictionary-values-string-length-summation/)

有时，在使用 Python 字典时，我们可能会遇到这样的问题:我们需要对所有字符串长度求和，这些长度以字典值的形式出现。这可以应用于许多领域，如网页开发和日常编程。让我们讨论执行这项任务的某些方法。

**方法#1:使用`sum() + generator expression + len()`**
上述功能的组合可用于执行该任务。在本文中，我们使用 len()计算长度，使用 sum()计算求和，使用生成器表达式计算迭代。

```py
# Python3 code to demonstrate working of 
# Dictionary values String Length Summation
# Using sum() + len() + generator expression
from collections import ChainMap

# initializing dictionary
test_dict = {'gfg' : '2345',
             'is' : 'abcde',
             'best' : 'qwerty'}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# Dictionary values String Length Summation
# Using sum() + len() + generator expression
res = sum((len(val) for val in test_dict.values()))

# printing result 
print("The string values length summation : " + str(res)) 
```

**Output :**

> 原始字典为:{'is': 'abcde '，' best': 'qwerty '，' gfg': '2345'}
> 字符串值长度总和:15