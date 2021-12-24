# Python–元组中最接近第 Kth 索引元素的对

> 原文:[https://www . geesforgeks . org/python-最接近对-kth-索引-元组中的元素/](https://www.geeksforgeeks.org/python-closest-pair-to-kth-index-element-in-tuple/)

有时，在处理 Python 记录时，我们可能会遇到一个问题，即我们需要找到最接近某个元组的元组，在特定索引上进行查询。这种问题可以应用于数据领域，例如 web 开发。让我们讨论执行这项任务的某些方法。

> **输入** :
> test_list = [(3，4)，(78，76)，(2，3)，(9，8)，(19，23)]
> tup = (17，23)
> K = 2
> 
> **输出** : (19，23)
> T3】输入 :
> test_list = [(3，4，9)，(5，6，7)]
> tup = (1，2，5)
> K = 3
> **输出** : (5，6，7)

**方法#1:使用`enumerate()` +循环**
以上功能的结合提供了蛮力的方式来解决这个问题。在这种情况下，我们使用 enumerate()来监视 index，使用 abs()来保持循环中每个元素的最小差异被检查。

```py
# Python3 code to demonstrate working of 
# Closest Pair to Kth index element in Tuple
# Using enumerate() + loop

# initializing list
test_list = [(3, 4), (78, 76), (2, 3), (9, 8), (19, 23)]

# printing original list
print("The original list is : " + str(test_list))

# initializing tuple
tup = (17, 23)

# initializing K 
K = 1

# Closest Pair to Kth index element in Tuple
# Using enumerate() + loop
min_dif, res = 999999999, None
for idx, val in enumerate(test_list):
    dif = abs(tup[K - 1] - val[K - 1])
    if dif < min_dif:
        min_dif, res = dif, idx

# printing result 
print("The nearest tuple to Kth index element is : " + str(test_list[res])) 
```

**Output :**

```py
The original list is : [(3, 4), (78, 76), (2, 3), (9, 8), (19, 23)]
The nearest tuple to Kth index element is : (19, 23)

```

**方法 2:使用`min()` + lambda**
以上功能的组合提供了解决这个问题的简写。在这种情况下，我们使用 min()来寻找最小元素差，并且使用 lambda 函数来执行迭代和计算。

```py
# Python3 code to demonstrate working of 
# Closest Pair to Kth index element in Tuple
# Using min() + lambda

# initializing list
test_list = [(3, 4), (78, 76), (2, 3), (9, 8), (19, 23)]

# printing original list
print("The original list is : " + str(test_list))

# initializing tuple
tup = (17, 23)

# initializing K 
K = 1

# Closest Pair to Kth index element in Tuple
# Using min() + lambda
res = min(range(len(test_list)), key = lambda sub: abs(test_list[sub][K - 1] - tup[K - 1]))

# printing result 
print("The nearest tuple to Kth index element is : " + str(test_list[res])) 
```

**Output :**

```py
The original list is : [(3, 4), (78, 76), (2, 3), (9, 8), (19, 23)]
The nearest tuple to Kth index element is : (19, 23)

```