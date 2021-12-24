# Python |组合两个字典为常用键添加值

> 原文:[https://www . geesforgeks . org/python-combine-two-dictionary-add-values-for-common-key/](https://www.geeksforgeeks.org/python-combine-two-dictionary-adding-values-for-common-keys/)

给定两个字典，任务是组合字典，以便我们在结果字典中获得公共键的附加值。

**例:**

```py
Input: dict1 = {'a': 12, 'for': 25, 'c': 9}
       dict2 = {'Geeks': 100, 'geek': 200, 'for': 300}

Output: {'for': 325, 'Geeks': 100, 'geek': 200}

```

让我们来看看完成这项任务的一些方法。

**法#1:** 天真法

```py
# Python program to combine two dictionary
# adding values for common keys
# initializing two dictionaries
dict1 = {'a': 12, 'for': 25, 'c': 9}
dict2 = {'Geeks': 100, 'geek': 200, 'for': 300}

# adding the values with common key
for key in dict2:
    if key in dict1:
        dict2[key] = dict2[key] + dict1[key]
    else:
        pass

print(dict2)
```

T5】输出:

```py
{'for': 325, 'Geeks': 100, 'geek': 200}

```

**方法 2:** 使用`**collections.Counter()**`

```py
# Python program to combine two dictionary
# adding values for common keys
from collections import Counter

# initializing two dictionaries
dict1 = {'a': 12, 'for': 25, 'c': 9}
dict2 = {'Geeks': 100, 'geek': 200, 'for': 300}

# adding the values with common key

Cdict = Counter(dict1) + Counter(dict2)
print(Cdict)
```

**输出:**

```py
Counter({'for': 325, 'geek': 200, 'Geeks': 100, 'a': 12, 'c': 9})

```

**方法三:**使用`**itertools.chain()**`

```py
# Python program to combine two dictionary
# adding values for common keys
import itertools 
import collections

# initializing two dictionaries
dict1 = {'a': 12, 'for': 25, 'c': 9}
dict2 = {'Geeks': 100, 'geek': 200, 'for': 300}

# using defaultdict
Cdict = collections.defaultdict(int)

# iterating key, val with chain()
for key, val in itertools.chain(dict1.items(), dict2.items()):
    Cdict[key] += val

print(dict(Cdict))
```

**输出:**

```py
{'for': 325, 'a': 12, 'geek': 200, 'Geeks': 100, 'c': 9}

```