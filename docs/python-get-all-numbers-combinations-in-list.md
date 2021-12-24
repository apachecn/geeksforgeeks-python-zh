# Python–获取列表中的所有数字组合

> 原文:[https://www . geesforgeks . org/python-get-all-numbers-in-list 组合/](https://www.geeksforgeeks.org/python-get-all-numbers-combinations-in-list/)

有时，在使用 Python 列表时，我们可能会遇到一个问题，即我们需要将每个数字与其他数字连接起来以创建新的数字。这种问题很特殊，但可以应用于许多领域，如日常编程和游戏。让我们讨论执行这项任务的某些方法。

> **输入** : test_list = [7，3，4，5]
> **输出** : [73，74，75，34，35，45]
> 
> **输入** : test_list = [2，5]
> **输出** : [25]

**方法#1:使用列表理解+ `combination()`**
以上功能的组合可以用来解决这个问题。在本文中，我们使用 combination()执行查找所有组合的任务，f-string 可用于执行串联。

```py
# Python3 code to demonstrate working of 
# All numbers combinations
# Using list comprehension + combinations
from itertools import combinations

# initializing list
test_list = [59, 236, 31, 38, 23]

# printing original list 
print("The original list : " + str(test_list))

# All numbers combinations
# Using list comprehension + combinations
res = [int(f"{x}{y}") for x, y in combinations(test_list, 2)]

# printing result 
print("All numbers combinations : " + str(res))
```

**Output :**

> 原列表:[59，236，31，38，23]
> 所有数字组合:[59236，5931，5938，5923，23631，23638，23623，3138，3123，3823]

**方法 2:使用 loop + `str() + int()`**
以上功能的组合可以用来解决这个问题。在本文中，我们使用强力和嵌套循环中的类型转换来执行形成组合的任务。这也输出反向组合。

```py
# Python3 code to demonstrate working of 
# All numbers combinations
# Using loop + str() + int()
from itertools import combinations

# initializing list
test_list = [59, 236, 31, 38, 23]

# printing original list 
print("The original list : " + str(test_list))

# All numbers combinations
# Using loop + str() + int()
res = []
for i in test_list:
    for j in test_list:
        if j != i:
           res.append(int(str(i) + str(j)))

# printing result 
print("All numbers combinations : " + str(res))
```

**Output :**

> 原列表:【59，236，31，38，23】
> 所有数字组合:【59236，5931，5938，5923，23659，23631，23638，23623，3159，31236，3138，3123，3859，38236，3831，3823，2359，23236，223