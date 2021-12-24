# Python |按值分组字典键

> 原文:[https://www . geesforgeks . org/python-group-dictionary-key-by-value/](https://www.geeksforgeeks.org/python-grouping-dictionary-keys-by-value/)

在字典上执行计算时，我们可能会遇到一个问题，我们可能必须执行根据值对键进行分组的任务，即创建一个键列表。在机器学习中组织数据的情况下也是如此。让我们讨论一下执行这项任务的具体方法。
**方法:使用排序的()+ items() + defaultdict()**
这个任务可以通过组合以上功能可以完成的任务来完成。defaultdict()用于创建一个用列表初始化的字典，items()获取键值对，而分组则由 sorted()帮助。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Grouping dictionary keys by value
# Using sorted() + items() + defaultdict()
from collections import defaultdict

# Initialize dictionary
test_dict = {'gfg' : 1, 'is' : 2, 'best' : 1, 'for' : 3, 'CS' : 2}

# printing original dictionary
print("The original dictionary : " +  str(test_dict))

# Using sorted() + items() + defaultdict()
# Grouping dictionary keys by value
res = defaultdict(list)
for key, val in sorted(test_dict.items()):
    res[val].append(key)

# printing result
print("Grouped dictionary is : " + str(dict(res)))
```

**输出:**

```
The original dictionary : {'gfg': 1, 'is': 2, 'best': 1, 'for': 3, 'CS': 2}
Grouped dictionary is : {2: ['CS', 'is'], 1: ['best', 'gfg'], 3: ['for']}
```

**方法二:**

此外，该任务也可以在不使用任何模块的情况下执行。
所以这里的逻辑是:
我们可以检查钥匙是否存在
1。不，然后我们可以创建密钥 res[v] = [i]
2。是的，我们可以在键 res[v] + [i]
上附加值

## 蟒蛇 3

```
d_input = {'Input.txt': 'Randy', 'Code.py': 'Stan', 'Output.txt': 'Randy'}
res = {}
for i, v in d_input.items():
    res[v] = [i] if v not in res.keys() else res[v] + [i]
print(res)
```

**输出:**

```
{'Randy': ['Input.txt', 'Output.txt'], 'Stan': ['Code.py']}
```