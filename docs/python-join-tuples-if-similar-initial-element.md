# Python–如果初始元素相似，则连接元组

> 原文:[https://www . geesforgeks . org/python-join-元组-if-相似-initial-element/](https://www.geeksforgeeks.org/python-join-tuples-if-similar-initial-element/)

有时，在使用 Python 元组时，我们可能会遇到一个问题，即我们需要根据初始元素的相似性来执行记录的串联。这个问题可以在数据科学等数据领域得到应用。让我们讨论执行这项任务的某些方法。

> **输入** : test_list = [(5，6)，(5，7)，(5，8)，(6，10)，(7，13)]
> **输出** : [(5，6，7，8)，(6，10)，(7，13)]
> 
> **输入** : test_list = [(5，6)，(6，7)，(6，8)，(6，10)，(7，13)]
> **输出** : [(5，6)，(6，7，8，10)，(7，13)]

**方法#1:使用循环**
这是完成这个任务的蛮力方式。在这种情况下，如果我们之前没有发现相似的元组值，我们就创建新的元组。切片用于将剩余元素添加到创建的元组中。

```py
# Python3 code to demonstrate working of 
# Join Tuples if similar initial element
# Using loop

# initializing list
test_list = [(5, 6), (5, 7), (6, 8), (6, 10), (7, 13)]

# printing original list
print("The original list is : " + str(test_list))

# Join Tuples if similar initial element
# Using loop
res = []
for sub in test_list:                                           
    if res and res[-1][0] == sub[0]:              
        res[-1].extend(sub[1:])                        
    else:
        res.append([ele for ele in sub])     
res = list(map(tuple, res))

# printing result 
print("The extracted elements : " + str(res)) 
```

**Output :**

```py
The original list is : [(5, 6), (5, 7), (6, 8), (6, 10), (7, 13)]
The extracted elements : [(5, 6, 7), (6, 8, 10), (7, 13)]

```

**方法 2:使用`defaultdict()` +循环**
以上功能的组合可以解决这个问题。上述方法的优点是，它减少了初始化新密钥的一次检查，并且即使相似的元素不连续也能很好地工作。

```py
# Python3 code to demonstrate working of 
# Join Tuples if similar initial element
# Using defaultdict() + loop
from collections import defaultdict

# initializing list
test_list = [(5, 6), (5, 7), (6, 8), (6, 10), (7, 13)]

# printing original list
print("The original list is : " + str(test_list))

# Join Tuples if similar initial element
# Using defaultdict() + loop
mapp = defaultdict(list)
for key, val in test_list:
    mapp[key].append(val)
res = [(key, *val) for key, val in mapp.items()]

# printing result 
print("The extracted elements : " + str(res)) 
```

**Output :**

```py
The original list is : [(5, 6), (5, 7), (6, 8), (6, 10), (7, 13)]
The extracted elements : [(5, 6, 7), (6, 8, 10), (7, 13)]

```