# Python–连接所有具有相似值的键

> 原文:[https://www . geesforgeks . org/python-concatenate-all-key-哪些具有相似的值/](https://www.geeksforgeeks.org/python-concatenate-all-keys-which-have-similar-values/)

给定一个带有字符串键和集合作为值的字典，任务是编写一个 python 程序来连接所有键，这些键具有相似的值顺序，而不考虑。

> **输入:** test_dict = {'gfg' : {5，4，3}，' is' : {4，3，5}，' best' : {1，4，3}，' for' : {1，3，4}，' geeks' : {1，2，3}}
> 
> **输出:** {'gfg-is': frozenset({3，4，5})，' best-for': frozenset({1，3，4})，' geeks': frozenset({1，2，3})}
> 
> **解释:**相似的集合键被连接，{5，4，3} == {4，3，5}，因此 gfg-is 被连接。
> 
> **输入:** test_dict = {'gfg' : {5，4，3}，' is' : {4，3，5}，' geeks' : {1，2，3}}
> 
> **输出:** {'gfg-is': frozenset({3，4，5})，' geeks': frozenset({1，2，3})}
> 
> **解释:**相似的集合键被连接，{5，4，3} == {4，3，5}，因此 gfg-is 被连接。

**方法#1:使用**[**default dict()**](https://www.geeksforgeeks.org/defaultdict-in-python/)**+**[**join()**](https://www.geeksforgeeks.org/join-function-python/)

在这种情况下，我们使用 defaultdict()执行散列每个集合和附加相应密钥的任务。下一步是将所有散列键连接到相似的集合值。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Concatenate similar set keys in Dictionary
# Using defaultdict() + join()
from collections import defaultdict

# initializing dictionary
test_dict = {'gfg': {5, 4, 3}, 'is': {4, 3, 5}, 'best': {
    1, 4, 3}, 'for': {1, 3, 4}, 'geeks': {1, 2, 3}}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

hash_vals = defaultdict(list)
for key, val in test_dict.items():

    # values are hashed using frozenset
    hash_vals[frozenset(val)].append(key)

# perform joining
res = {'-'.join(keys): vals for (vals, keys) in hash_vals.items()}

# printing result
print("The concatenated keys : " + str(res))
```

**输出:**

> 原始字典为:{'gfg': {3，4，5}，' is': {3，4，5}，' best': {1，3，4}，' for': {1，3，4}，' geeks': {1，2，3}}
> 
> 串联键:{“gfg-is”:frozen set({ 3，4，5})，“best-for”:frozen set({ 1，3，4})，“geeks”:frozen set({ 1，2，3})}

**方法二:使用**[**group by()**](https://www.geeksforgeeks.org/itertools-groupby-in-python/)**+**[**join()**](https://www.geeksforgeeks.org/join-function-python/)**+**[**词典理解**](https://www.geeksforgeeks.org/python-dictionary-comprehension/)

在本文中，我们使用 groupby()执行类似元素的分组任务。之后，使用 join()连接相似值的键。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Concatenate similar set keys in Dictionary
# Using groupby() + join() + dictionary comprehension
from itertools import groupby

# initializing dictionary
test_dict = {'gfg': {5, 4, 3}, 'is': {4, 3, 5},
             'best': {1, 4, 3}, 'for': {1, 3, 4},
             'geeks': {1, 2, 3}}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# elements grouped using groupby()
# dictionary comprehension provides shorthand to perform grouping
res = {'-'.join(val): key for key, val in groupby(
  sorted(test_dict, key=test_dict.get), key=lambda sub: test_dict[sub])}

# printing result
print("The concatenated keys : " + str(res))
```

**输出:**

> 原始字典为:{'gfg': {3，4，5}，' is': {3，4，5}，' best': {1，3，4}，' for': {1，3，4}，' geeks': {1，2，3}}
> 
> 串联键:{'gfg-is': {3，4，5}，'最佳':{1，3，4}，'极客':{1，2，3}}