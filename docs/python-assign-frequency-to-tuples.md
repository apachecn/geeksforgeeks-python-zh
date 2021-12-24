# Python–为元组分配频率

> 原文:[https://www . geesforgeks . org/python-将频率分配给元组/](https://www.geeksforgeeks.org/python-assign-frequency-to-tuples/)

给定元组列表，为列表中的每个元组分配频率。

> **输入** : test_list = [(6，5，8)，(2，7)，(6，5，8)，(9)，(2，7)]
> **输出** : [(6，5，8，2)，(2，7，2)，(9，1)]
> **解释** : (2，7)出现 2 次，因此元组中出现 2。
> 
> **输入** : test_list = [(2，7)，(2，7)，(6，5，8)，(9)，(2，7)]
> **输出** : [(6，5，8，1)，(2，7，3)，(9，1)]
> **解释** : (2，7)出现 3 次，因此元组中出现 3。

**方法一:使用 Counter() + items() + *运算符+列表理解**

在这种情况下，我们使用 Counter()提取频率，使用 items()提取频率号，使用*运算符解包元素，并使用列表理解将其分配给元组列表中的所有元素。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Assign Frequency to Tuples
# Using Counter() + items() + * operator + list comprehension
from collections import Counter

# initializing list
test_list = [(6, 5, 8), (2, 7), (6, 5, 8), (6, 5, 8), (9, ), (2, 7)]

# printing original list
print("The original list is : " + str(test_list))

# one-liner to solve problem
# assign Frequency as last element of tuple
res = [(*key, val) for key, val in Counter(test_list).items()]

# printing results
print("Frequency Tuple list : " + str(res))
```

**Output**

```
The original list is : [(6, 5, 8), (2, 7), (6, 5, 8), (6, 5, 8), (9, ), (2, 7)]
Frequency Tuple list : [(6, 5, 8, 3), (2, 7, 2), (9, 1)]

```

**方法 2:使用最常用的()+ Counter() + *运算符+列表理解**

这类似于上面的方法，只是 most_common()对 list 执行排序操作，这是不必要的。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Assign Frequency to Tuples
# Using most_common() + Counter() + * operator + list comprehension
from collections import Counter

# initializing list
test_list = [(6, 5, 8), (2, 7), (6, 5, 8), (6, 5, 8), (9, ), (2, 7)]

# printing original list
print("The original list is : " + str(test_list))

# most_common performs sort on arg. list
# assign Frequency as last element of tuple
res = [(*key, val) for key, val in Counter(test_list).most_common()]

# printing results
print("Frequency Tuple list : " + str(res))
```

**Output**

```
The original list is : [(6, 5, 8), (2, 7), (6, 5, 8), (6, 5, 8), (9, ), (2, 7)]
Frequency Tuple list : [(6, 5, 8, 3), (2, 7, 2), (9, 1)]

```