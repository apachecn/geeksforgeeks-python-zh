# Python–查找第 k 个偶数元素

> 原文:[https://www.geeksforgeeks.org/python-find-kth-even-element/](https://www.geeksforgeeks.org/python-find-kth-even-element/)

给定一个列表，提取偶数元素的第 k 次出现。

> **输入** : test_list = [4，6，2，3，8，9，10，11]，K = 3
> **输出** : 8
> **解释** : K = 3，即基于 0 的索引，4，6，2，4 是 8。
> 
> **输入** : test_list = [4，6，2，3，8，9，10，11]，K = 2
> **输出** : 2
> **解释** : K = 2，即基于 0 的索引，4，6，3 是 2。

**方法一:使用列表理解**

在本文中，我们使用%运算符提取偶数元素列表，并使用列表索引访问来获取 Kth 偶数元素。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Kth Even Element
# Using list comprehension

# initializing list
test_list = [4, 6, 2, 3, 8, 9, 10, 11]

# printing original list
print("The original list is : " + str(test_list))

# initializing K 
K = 4

# list comprehension to perform iteration and % 2 check 
res = [ele for ele in test_list if ele % 2 == 0][K]

# printing result 
print("The Kth Even Number : " + str(res))
```

**Output**

```py
The original list is : [4, 6, 2, 3, 8, 9, 10, 11]
The Kth Even Number : 10

```

**方法 2:使用过滤器()+λ**

在这种情况下，寻找偶数元素的任务是使用 filter() + lambda 函数完成的。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Kth Even Element
# Using filter() + lambda

# initializing list
test_list = [4, 6, 2, 3, 8, 9, 10, 11]

# printing original list
print("The original list is : " + str(test_list))

# initializing K 
K = 4

# list comprehension to perform iteration and % 2 check 
res = list(filter(lambda ele : ele % 2 == 0, test_list))[K]

# printing result 
print("The Kth Even Number : " + str(res))
```

**Output**

```py
The original list is : [4, 6, 2, 3, 8, 9, 10, 11]
The Kth Even Number : 10

```