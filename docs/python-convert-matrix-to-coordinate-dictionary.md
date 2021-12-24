# Python–将矩阵转换为坐标字典

> 原文:[https://www . geesforgeks . org/python-convert-matrix-to-coordinate-dictionary/](https://www.geeksforgeeks.org/python-convert-matrix-to-coordinate-dictionary/)

有时，在使用 Python 字典时，我们可能会遇到需要执行矩阵元素到其坐标列表的转换的问题。这种问题可能出现在许多领域，包括日常编程和竞争性编程。让我们讨论执行这项任务的某些方法。

> **输入** : test_list = [['g '，' g '，' g']，['g '，' g '，' g']]
> **输出** : {'g': {(0，1)，(1，2)，(0，0)，(1，1)，(1，0)，(0，2)}}
> 
> **输入** : test_list = [['a '，' b '，' c']]
> **输出** : {'a': {(0，0)}，' b': {(0，1)}，' c': {(0，2)}}

**方法#1:使用循环+ `enumerate()`**
上述功能的组合可用于执行该任务。在本文中，我们使用蛮力来提取元素，并在 enumerate()的帮助下为它们分配索引。

```py
# Python3 code to demonstrate working of 
# Convert Matrix to Coordinate Dictionary
# Using loop + enumerate()

# initializing list
test_list = [['g', 'f', 'g'], ['i', 's', 'g'], ['b', 'e', 's', 't']]

# printing original list
print("The original list is : " + str(test_list))

# Convert Matrix to Coordinate Dictionary
# Using loop + enumerate()
res = dict()
for idx, sub in enumerate(test_list):
    for j, ele in enumerate(sub):
        if ele in res:
            res[ele].add((idx, j))
        else:
            res[ele] = {(idx, j)}

# printing result 
print("The Coordinate Dictionary : " + str(res)) 
```

**Output :**

> 原列表为:[['g '，' f '，' g']，['i '，' s '，' g']，['b '，' e '，' s '，' t ']
> 坐标字典:{'g': {(1，2)，(0，0)，(0，2)}，' f': {(0，1)}，' t': {(2，3)}，' i': {(1，0)}，' b': {(2，0)}，' e': {(2，1)}，，

**方法 2:使用`setdefault()` +循环**
这个方法的操作方式和上面类似，只是不同的是`setdefault()`减少了记忆元素值和键存在检查的任务。

```py
# Python3 code to demonstrate working of 
# Convert Matrix to Coordinate Dictionary
# Using setdefault() + loop

# initializing list
test_list = [['g', 'f', 'g'], ['i', 's', 'g'], ['b', 'e', 's', 't']]

# printing original list
print("The original list is : " + str(test_list))

# Convert Matrix to Coordinate Dictionary
# Using setdefault() + loop
res = dict()
for idx, ele in enumerate(test_list):
    for j, sub in enumerate(ele):
        res.setdefault(sub, set()).add((idx, j))

# printing result 
print("The Coordinate Dictionary : " + str(res)) 
```

**Output :**

> 原列表为:[['g '，' f '，' g']，['i '，' s '，' g']，['b '，' e '，' s '，' t ']
> 坐标字典:{'g': {(1，2)，(0，0)，(0，2)}，' f': {(0，1)}，' t': {(2，3)}，' i': {(1，0)}，' b': {(2，0)}，' e': {(2，1)}，，