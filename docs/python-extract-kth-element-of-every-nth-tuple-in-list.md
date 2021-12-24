# Python–提取列表中每第 n 个元组的第 k 个元素

> 原文:[https://www . geeksforgeeks . org/python-extract-kth-每 n 个元组中的元素列表/](https://www.geeksforgeeks.org/python-extract-kth-element-of-every-nth-tuple-in-list/)

给定元组列表，提取每第 n 个元组的 Kth 列元素。

> **输入** :test_list = [(4，5，3)，(3，4，7)，(4，3，2)，(4，7，8)，(6，4，7)，(2，5，7)，(1，9，10)，(3，5，7)]，K = 2，N = 3
> **输出**:【3，8，10】
> **解释**:从第 0，3，6 元组开始，第 2 个元素为 3，8，10。
> 
> **输入** :test_list = [(4，5，3)，(3，4，7)，(4，3，2)，(4，7，8)，(6，4，7)，(2，5，7)，(1，9，10)，(3，5，7)]，K = 0，N = 3
> **输出**:【4，4，1】
> **解释**:从第 0，3，6 元组开始，第 0 个元素为 4，4，1。

**方法#1:使用循环**

在本文中，我们通过使用 range()的第三个参数跳过 N 个值进行迭代，并使用循环追加列表中的每个 Kth 值。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Extract Kth element of every Nth tuple in List
# Using loop

# initializing list
test_list = [(4, 5, 3), (3, 4, 7), (4, 3, 2), (4, 7, 8),
             (6, 4, 7), (2, 5, 7), (1, 9, 10), (3, 5, 7)]

# printing original list
print("The original list is : " + str(test_list))

# initializing K
K = 1

# initializing N 
N = 3

res = []
for idx in range(0, len(test_list), N):

    # extract Kth element
    res.append(test_list[idx][K])

# printing result 
print("The extracted elements : " + str(res))
```

**Output**

```
The original list is : [(4, 5, 3), (3, 4, 7), (4, 3, 2), (4, 7, 8), (6, 4, 7), (2, 5, 7), (1, 9, 10), (3, 5, 7)]
The extracted elements : [5, 7, 9]

```

**方法 2:使用列表理解**

在这种情况下，我们使用与上面相同的方法，使用列表理解，使用单行执行提取元素的任务。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Extract Kth element of every Nth tuple in List
# Using list comprehension

# initializing list
test_list = [(4, 5, 3), (3, 4, 7), (4, 3, 2), (4, 7, 8),
             (6, 4, 7), (2, 5, 7), (1, 9, 10), (3, 5, 7)]

# printing original list
print("The original list is : " + str(test_list))

# initializing K
K = 1

# initializing N 
N = 3

# Skipping N using 3rd param of range()
res = [test_list[idx][K] for idx in range(0, len(test_list), N)]

# printing result 
print("The extracted elements : " + str(res))
```

**Output**

```
The original list is : [(4, 5, 3), (3, 4, 7), (4, 3, 2), (4, 7, 8), (6, 4, 7), (2, 5, 7), (1, 9, 10), (3, 5, 7)]
The extracted elements : [5, 7, 9]

```