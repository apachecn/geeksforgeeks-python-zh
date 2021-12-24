# Python–将元组连接到元组列表中的整数

> 原文:[https://www . geesforgeks . org/python-join-tuple-to-integer-in-tuple-list/](https://www.geeksforgeeks.org/python-join-tuples-to-integers-in-tuple-list/)

有时，在处理 Python 记录时，我们可能会遇到一个问题，即我们需要串联所有元素，以便将列表中元组中的元素转换为整数。这种问题可以应用于许多领域，如日常和竞争性编程。让我们讨论执行这项任务的某些方法。

> **输入** : test_list = [(4，5，6)，(5，1)，(1，3，8，0)，(6，9)]
> **输出**:【456，51，1380，69】
> 
> **输入** : test_list = [(4，5，6，8，9)]
> **输出**:【45689】

**方法#1:使用循环**
这是可以执行该任务的蛮力方法。在这种情况下，我们使用数字创建执行所有元素的连接，以数学方式计算结果。

```
# Python3 code to demonstrate working of 
# Join Tuples to Integers in Tuple List
# Using loop

# helpr_fnc
def join_tup(tup):
    res = tup[0]
    for idx in tup[1:]:
        res = res * 10 + idx
    return res

# initializing list
test_list = [(4, 5), (5, 6), (1, 3), (6, 9)]

# printing original list
print("The original list is : " + str(test_list))

# Join Tuples to Integers in Tuple List
# Using loop
res = [join_tup(idx) for idx in test_list]

# printing result 
print("The joined result : " + str(res)) 
```

**Output :**

```
The original list is : [(4, 5), (5, 6), (1, 3), (6, 9)]
The joined result : [45, 56, 13, 69]

```

**方法 2:使用`map() + join() + int()`**
以上功能的组合可以用来解决问题。在这种情况下，我们通过字符串转换来执行连接，使用 join()和 int()的连接用于将结果转换回整数。

```
# Python3 code to demonstrate working of 
# Join Tuples to Integers in Tuple List
# Using map() + join() + int()

# initializing list
test_list = [(4, 5), (5, 6), (1, 3), (6, 9)]

# printing original list
print("The original list is : " + str(test_list))

# Join Tuples to Integers in Tuple List
# Using map() + join() + int()
res = [int(''.join(map(str, idx))) for idx in test_list]

# printing result 
print("The joined result : " + str(res)) 
```

**Output :**

```
The original list is : [(4, 5), (5, 6), (1, 3), (6, 9)]
The joined result : [45, 56, 13, 69]

```