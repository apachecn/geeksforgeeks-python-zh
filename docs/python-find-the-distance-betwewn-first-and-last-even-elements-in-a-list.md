# Python–找出列表中第一个和最后一个偶数元素之间的距离

> 原文:[https://www . geesforgeks . org/python-查找列表中第一个和最后一个偶数元素之间的距离/](https://www.geeksforgeeks.org/python-find-the-distance-betwewn-first-and-last-even-elements-in-a-list/)

给定一个列表，编写一个 Python 程序来查找列表中偶数元素的跨度，即偶数元素第一次出现和最后一次出现之间的距离。

**示例:**

> **输入** : test_list = [1，3，7，4，7，2，9，1，10，11]
> **输出** : 5
> **解释**:偶数元素从 4 开始到 10 结束，跨越 5 个指数。
> 
> **输入** : test_list = [1，3，7，4，7，2，9，1，1，11]
> **输出** : 2
> **解释**:偶数元素从 4 开始到 2 结束，跨越 2 个索引。

**方法一:使用** [**列表理解**](https://www.geeksforgeeks.org/python-list-comprehension/)

在这种情况下，我们使用列表理解获得所有偶数元素的所有索引，然后执行列表中匹配元素的第一个和最后一个索引的差异。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Even elements span in list
# Using list comprehension

# initializing Matrix
test_list = [1, 3, 7, 4, 7, 2, 9, 1, 10, 11]

# printing original list
print("The original list is : " + str(test_list))

# getting even indices
indices_list = [idx for idx in range(
    len(test_list)) if test_list[idx] % 2 == 0]

# getting difference of first and last occurrence
res = indices_list[-1] - indices_list[0]

# printing result
print("Even elements span : " + str(res))
```

**Output**

```
The original list is : [1, 3, 7, 4, 7, 2, 9, 1, 10, 11]
Even elements span : 5
```

**方法 2:使用** [**滤镜()**](https://www.geeksforgeeks.org/filter-in-python/)**+**[**λ**](https://www.geeksforgeeks.org/python-lambda/)

在本文中，我们使用 filter()和 lambda 执行获取元素索引的任务。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Even elements span in list
# Using filter() + lambda

# initializing Matrix
test_list = [1, 3, 7, 4, 7, 2, 9, 1, 10, 11]

# printing original list
print("The original list is : " + str(test_list))

# getting even indices
indices_list = list(
    filter(lambda x: test_list[x] % 2 == 0, range(len(test_list))))

# getting difference of first and last occurrence
res = indices_list[-1] - indices_list[0]

# printing result
print("Even elements span : " + str(res))
```

**Output**

```
The original list is : [1, 3, 7, 4, 7, 2, 9, 1, 10, 11]
Even elements span : 5
```