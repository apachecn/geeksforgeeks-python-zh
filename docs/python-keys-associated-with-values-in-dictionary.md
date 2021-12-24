# Python–与字典中的值相关联的键

> 原文:[https://www . geesforgeks . org/python-key-associated-in-values-dictionary/](https://www.geeksforgeeks.org/python-keys-associated-with-values-in-dictionary/)

有时候，在使用 Python 字典时，我们可能会遇到一些问题，需要对字典进行改造，即所有值都指向它们所属的键。这种问题可能发生在许多领域，包括 web 开发和数据领域。让我们讨论执行这项任务的特定方式。

> **输入:** test_dict = {'abc' : [10，30]，' bcd' : [30，40，10]}
> **输出:** {10: ['abc '，' bcd']，30: ['abc '，' bcd']，40: ['bcd']}
> 
> **输入:** test_dict = {'gfg' : [1，2，3]，' is' : [1，4]，' best' : [4，2]}
> **输出:** {1: ['is '，' gfg']，2: ['gfg '，' best']，3: ['gfg']，4: ['is '，' best']

**方法:使用`defaultdict()` +循环**
以上功能的组合可以解决这个问题。在这种情况下，我们创建列表的 defaultdict，并通过使用蛮力方法检查外观内部的关联来插入元素。

```
# Python3 code to demonstrate working of 
# Values Associated Keys
# Using defaultdict() + loop
from collections import defaultdict

# initializing dictionary
test_dict = {'gfg' : [1, 2, 3], 'is' : [1, 4], 'best' : [4, 2]} 

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# Values Associated Keys
# Using defaultdict() + loop
res = defaultdict(list)
for key, val in test_dict.items():
    for ele in val:
        res[ele].append(key)

# printing result 
print("The values associated dictionary : " + str(dict(res))) 
```

**Output :**

```
The original dictionary is : {'is': [1, 4], 'gfg': [1, 2, 3], 'best': [4, 2]}
The values associated dictionary : {1: ['is', 'gfg'], 2: ['gfg', 'best'], 3: ['gfg'], 4: ['is', 'best']}

```