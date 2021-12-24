# Python–K 连续最大值

> 原文:[https://www.geeksforgeeks.org/python-k-consecutive-maximum/](https://www.geeksforgeeks.org/python-k-consecutive-maximum/)

给定一个列表，从每个索引中找到最多的下一个 K 个元素。

> **输入**:test _ list =【4，3，9，2，6，12，4，3，2，4，5】，K = 4
> **输出**:【9，9，9，12，12，12，4，5】
> **解释**:后面 4 个元素的最大值，(最大值(4，3，9，2) = 9)
> 
> **输入**:test _ list =【4，3，9，2，6】，K = 4
> **输出**:【9，9】
> **解释**:后面 4 个元素的最大值，(max(4，3，9，2) = 9)

**方法#1:使用循环+ max() +切片**

在这种情况下，我们对循环中的元素进行迭代，切片到下一个 K，并使用 max()获得当前索引的最大值。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# K consecutive Maximum 
# Using max() + loop + slicing

# initializing list
test_list = [4, 3, 8, 2, 6, 7, 4, 3, 2, 4, 5]

# printing original list
print("The original list is : " + str(test_list))

# initializing K 
K = 4

res = []
for idx in range(len(test_list) - K + 1):

    # slice next K and compute Maximum
    res.append(max(test_list[idx : idx + K]))

# printing result 
print("Next K Maximum List : " + str(res))
```

**Output**

```py
The original list is : [4, 3, 8, 2, 6, 7, 4, 3, 2, 4, 5]
Next K Maximum List : [8, 8, 8, 7, 7, 7, 4, 5]

```

**方法 2:使用列表理解**

这是解决这个问题的另一种方法，使用列表理解的上述方法的一行替代方法。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# K consecutive Maximum 
# Using list comprehension

# initializing list
test_list = [4, 3, 8, 2, 6, 7, 4, 3, 2, 4, 5]

# printing original list
print("The original list is : " + str(test_list))

# initializing K 
K = 4

# one-liner to solve problem
res = [max(test_list[idx : idx + K]) for idx in range(len(test_list) - K + 1)]

# printing result 
print("Next K Maximum List : " + str(res))
```

**Output**

```py
The original list is : [4, 3, 8, 2, 6, 7, 4, 3, 2, 4, 5]
Next K Maximum List : [8, 8, 8, 7, 7, 7, 4, 5]

```