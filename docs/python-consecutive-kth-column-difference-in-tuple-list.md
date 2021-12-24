# Python–元组列表中连续第 Kth 列差异

> 原文:[https://www . geesforgeks . org/python-continuous-kth-column-in-difference-tuple-list/](https://www.geeksforgeeks.org/python-consecutive-kth-column-difference-in-tuple-list/)

有时候，在使用 Python 列表时，我们可以有一个任务，其中我们需要使用元组列表，并获得其 Kth 索引的绝对差异。当处理数据信息时，这个问题在 web 开发领域有应用。让我们讨论执行这项任务的某些方法。

**示例:**

> **输入** : test_list = [(5，4，2)，(1，3，4)，(5，7，8)，(7，4，3)]，K = 0
> **输出**:【4，4，2】
> **解释**:5–1 = 4，故名 4。
> 
> **输入** : test_list = [(5，4，2)，(1，3，4)，(5，7，8)，(7，4，3)]，K = 2
> **输出**:【2，4，5】
> **解释**:8–3 = 5，故名 5。

**方法#1:使用循环**

在这种情况下，对于每个元组，我们减去并找到列表中具有连续元组的 Kth 列元组的绝对差。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Consecutive Kth column Difference in Tuple List
# Using loop

# initializing list
test_list = [(5, 4, 2), (1, 3, 4), (5, 7, 8), (7, 4, 3)]

# printing original list
print("The original list is : " + str(test_list))

# initializing K 
K = 1 

res = []
for idx in range(0, len(test_list) - 1):

    # getting difference using abs()
    res.append(abs(test_list[idx][K] - test_list[idx + 1][K]))

# printing result 
print("Resultant tuple list : " + str(res))
```

**输出:**

> 原始列表为:[(5，4，2)，(1，3，4)，(5，7，8)，(7，4，3)]
> 结果元组列表:[1，4，3]

**方法二:使用 zip() +列表理解**

在本文中，我们使用列表理解迭代列表中的所有元素，并使用 zip()比较成对的元素。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Consecutive Kth column Difference in Tuple List
# Using zip() + list comprehension

# initializing list
test_list = [(5, 4, 2), (1, 3, 4), (5, 7, 8), (7, 4, 3)]

# printing original list
print("The original list is : " + str(test_list))

# initializing K 
K = 1 

# zip used to pair each tuple with subsequent tuple
res = [abs(x[K] - y[K]) for x, y in zip(test_list, test_list[1:])]

# printing result 
print("Resultant tuple list : " + str(res))
```

**输出:**

> 原始列表为:[(5，4，2)，(1，3，4)，(5，7，8)，(7，4，3)]
> 结果元组列表:[1，4，3]