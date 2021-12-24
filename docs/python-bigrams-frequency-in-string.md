# Python–字符串中的二元模型频率

> 原文:[https://www . geesforgeks . org/python-bigrams-in-frequency-in-string/](https://www.geeksforgeeks.org/python-bigrams-frequency-in-string/)

有时在使用 Python 数据时，我们会遇到需要从字符串中提取二元模型的问题。这在自然语言处理领域有应用。但有时，我们需要计算数据收集的独特二元模型的频率。这个问题的解决方案可能是有用的。让我们讨论执行这项任务的某些方法。

**方法#1:使用`Counter()` +生成器表达式**
以上功能的组合可以解决这个问题。在本文中，我们使用 Counter()计算频率，使用生成器表达式和字符串切片计算二元模型。

```
# Python3 code to demonstrate working of 
# Bigrams Frequency in String
# Using Counter() + generator expression
from collections import Counter

# initializing string
test_str = 'geeksforgeeks'

# printing original string
print("The original string is : " + str(test_str))

# Bigrams Frequency in String
# Using Counter() + generator expression
res = Counter(test_str[idx : idx + 2] for idx in range(len(test_str) - 1))

# printing result 
print("The Bigrams Frequency is : " + str(dict(res))) 
```

**Output :**

> 原始字符串为:geeksforgeeks
> Bigrams 的频率为:{“ee”:2，“ks”:2，“ek”:2，“SF”:1，“fo”:1，“ge”:2，“rg”:1，“or”:1 }