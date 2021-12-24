# Python–找出矩阵中缺失的列表元素之和的差值，反之亦然

> 原文:[https://www . geesforgeks . org/python-找到矩阵中缺少的列表元素之和的差异，反之亦然/](https://www.geeksforgeeks.org/python-find-the-difference-of-the-sum-of-list-elements-that-are-missing-from-matrix-and-vice-versa/)

给定一个列表和一个矩阵，任务是编写一个 Python 程序，该程序可以找到矩阵中缺少的列表元素之和的差，反之亦然。

一个更简单的解释是，找到矩阵中所有的元素并求和，但不在列表中。接下来，找出列表中所有不在矩阵中的元素并求和。执行提取的和值之间的差值。

> **输入** : test_list = [[2，4，1]，[8，1，2]，[9，1，10]，[4，3，2]]，tar_list = [2，3，10，7，5，4]
> **输出** : 8
> **解释** : 8 + 9 + 1 + 1 + 1 = 20【矩阵中的元素，不在列表中】
> 7 + 5 = 12【列表中的元素，不在矩阵中】
> 
> **输入:** test_list = [[2]，[8]，[9]，[4]]，tar_list = [2，3，10，7，5，4]
> **输出** : 8
> **说明:** 8 + 9 = 17【矩阵中的元素，不在列表中】
> 3 + 10 + 7 + 5 = 25【列表中的元素，不在矩阵中】
> 差值= 25–17 = 8。

**方法 1 :** *使用* [*循环*](https://www.geeksforgeeks.org/loops-in-python/) *和*[*from _ iterable()*](https://www.geeksforgeeks.org/python-itertools-chain-from_iterable/)

在这种情况下，我们使用循环中的计数器得到列表中存在的元素的列表和，而不是矩阵，反之亦然，并计算差值。from_iterable()用于展平矩阵。

**示例:**

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Missing elements difference from Matrix and List
# Using loop
from itertools import chain

# initializing list
test_list = [[2, 4, 1], [8, 1, 2], [9, 1, 10], [4, 3, 2]]

# printing original list
print("The original list is : " + str(test_list))

# initializing target list
tar_list = [2, 3, 10, 7, 5, 4]

# flattening Matrix
flat_mat = list(chain.from_iterable(test_list))

# getting sum of list elements not in Matrix
list_sum = 0
for ele in tar_list:
    if ele not in flat_mat:
        list_sum += ele

# getting sum of Matrix elements not in list
mat_sum = 0
for ele in flat_mat:
    if ele not in tar_list:
        mat_sum += ele

# computing difference
res = abs(mat_sum - list_sum)

# printing result
print("The computed count : " + str(res))
```

**输出:**

> 原来的名单是:[[ 2，4，1]，[8，1，2]，[8，1，2]，[9，1，10]，[4，3，2]]
> 
> 计算的计数:8

**方法二:** *使用* [*求和()*](https://www.geeksforgeeks.org/sum-function-python/#:~:text=Python%20provide%20an%20inbuilt%20function,of%20numbers%20in%20the%20iterable.) *和*[*from _ iterable()*](https://www.geeksforgeeks.org/python-itertools-chain-from_iterable/)

在这种情况下，计算总和的任务是使用 sum()完成的，其余所有功能都以与上述方法相同的方式执行。

**示例:**

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Missing elements difference from Matrix and List
# Using sum() + from_iterable()
from itertools import chain

# initializing list
test_list = [[2, 4, 1], [8, 1, 2], [9, 1, 10], [4, 3, 2]]

# printing original list
print("The original list is : " + str(test_list))

# initializing target list
tar_list = [2, 3, 10, 7, 5, 4]

# flattening Matrix
flat_mat = list(chain.from_iterable(test_list))

# getting sum of list elements not in Matrix
list_sum = sum([ele for ele in tar_list if ele not in flat_mat])

# getting sum of Matrix elements not in list
mat_sum = sum([ele for ele in flat_mat if ele not in tar_list])

# computing difference
res = abs(mat_sum - list_sum)

# printing result
print("The computed count : " + str(res))
```

**输出:**

> 原始列表为:[[2，4，1]，[8，1，2]，[9，1，10]，[4，3，2]]
> 
> 计算的计数:8