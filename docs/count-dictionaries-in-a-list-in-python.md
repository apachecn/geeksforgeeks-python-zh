# 用 Python 对列表中的字典进行计数

> 原文:[https://www . geesforgeks . org/count-python 列表中的字典/](https://www.geeksforgeeks.org/count-dictionaries-in-a-list-in-python/)

Python 中的[列表可能有不同类型的项目。有时，在处理数据时，我们可能会遇到一个问题，即我们需要在特定的列表中找到字典的数量。这可以应用于数据领域，包括网络开发和机器学习。让我们讨论执行这项任务的某些方法。](https://www.geeksforgeeks.org/python-list/)

> **输入** : test_list = [4，5，' gfg']
> **输出** : 0
> 
> **输入**:test _ list =[{ ' gfg ':1 }]
> **输出** : 1
> 
> **输入** : test_list = [10，{'gfg' : 1}，{'ide' : 2，' code' : 3}，20]
> **输出** : 2
> 
> **输入** : test_list = [4，5，' gfg '，{'best': 32，' gfg': 1}，{'CS': 4}，(1，2)]
> **输出** : 2

**方法#1:使用列表理解+ `isinstance()`**
以上功能的组合可以用来解决这个问题。在本文中，我们使用列表理解执行迭代，并使用 isinstance()测试字典。

```
# Python3 code to demonstrate working of 
# Dictionary Count in List
# Using list comprehension + isinstance()

# initializing list
test_list = [10, {'gfg' : 1}, {'ide' : 2, 'code' : 3}, 20]

# printing original list
print("The original list is : " + str(test_list))

# Dictionary Count in List
# Using list comprehension + isinstance()
res = len([ele for ele in test_list if isinstance(ele, dict)])

# printing result 
print("The Dictionary count : " + str(res)) 
```

**Output:**

```
The original list is : [10, {'gfg': 1}, {'code': 3, 'ide': 2}, 20]
The Dictionary count : 2

```

**方法 2:使用递归+ `isinstance()`(对于嵌套词典)**
以上功能的组合可以用来解决这个问题。在这方面，我们还利用递归解决了内部嵌套问题。

```
# Python3 code to demonstrate working of 
# Dictionary Count in List
# Using recursion + isinstance()

# helper_func
def hlper_fnc(test_list):
    count = 0
    if isinstance(test_list, str):
        return 0
    if isinstance(test_list, dict):
        return hlper_fnc(test_list.values()) + hlper_fnc(test_list.keys()) + 1
    try:
        for idx in test_list:
            count = count + hlper_fnc(idx)
    except TypeError:
        return 0
    return count

# initializing list
test_list = [10, {'gfg': 1}, {'code': 3, 'ide': 2}, 20]

# printing original list
print("The original list is : " + str(test_list))

# Dictionary Count in List
# Using recursion + isinstance()
res = hlper_fnc(test_list)

# printing result 
print("The Dictionary count : " + str(res)) 
```

**Output:**

```
The original list is : [10, {'gfg': 1}, {'code': 3, 'ide': 2}, 20]
The Dictionary count : 2

```