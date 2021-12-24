# Python |两个字典键的区别

> 原文:[https://www . geesforgeks . org/python-两个字典的键差/](https://www.geeksforgeeks.org/python-difference-in-keys-of-two-dictionaries/)

给定两个字典 *dic1* 和 *dic2* ，它们可能包含相同的键，找出给定字典中键的区别。

**代码#1 :** 使用 set 查找缺少的*键。*

```
*# Python code to find the difference in
# keys in two dictionary

# Initialising dictionary 
dict1= {'key1':'Geeks', 'key2':'For', 'key3':'geeks'}
dict2= {'key1':'Geeks', 'key2:':'Portal'}

diff = set(dict2) - set(dict1)

# Printing difference in
# keys in two dictionary
print(diff)*
```

***输出:***

```
{'key2:'}

```