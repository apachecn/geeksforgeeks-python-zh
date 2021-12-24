# Python–提取极值差大于 K 的列表

> 原文:[https://www . geesforgeks . org/python-extract-list-带极值差-大于-k/](https://www.geeksforgeeks.org/python-extract-list-with-difference-in-extreme-values-greater-than-k/)

给定一个列表。任务是过滤最小值和最大值之差大于 k 的所有行

**示例:**

> **输入** : test_list = [[13，5，1]，[9，1，2]，[3，4，2]，[1，10，2]]，K = 5
> **输出** : [[9，1，2]，[1，10，2]，[13，5，1]]
> **解释** : 8，9，12 为差异，大于 K
> 
> **输入** : test_list = [[13，5，1]，[9，1，2]，[3，4，2]，[1，10，2]]，K = 15
> **输出** : []
> **解释**:没有带 diff > K 的列表

**方法一:使用** [**列表理解**](https://www.geeksforgeeks.org/python-list-comprehension-and-slicing/)**+**[**min()**](https://www.geeksforgeeks.org/python-min-function/)**+**[**max()**](https://www.geeksforgeeks.org/python-max-function/)

在这种情况下，我们使用列表理解执行迭代任务，使用比较运算符执行检查任务。使用最大()和最小()计算值。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Filter rows with Extreme values greater than K
# Using min() + max() + list comprehension

# initializing list
test_list = [[3, 5, 1], [9, 1, 2], [3, 4, 2], [1, 10, 2]]

# printing original list
print("The original list is : " + str(test_list))

# initializing K 
K = 5

# max() and min() getting extreme difference
res = [sub for sub in test_list if max(sub) - min(sub) > K]

# printing result 
print("Filtered rows : " + str(res))
```

**输出:**

> 原始列表为:[[3，5，1]，[9，1，2]，[3，4，2]，[1，10，2]]
> 过滤行:[[9，1，2]，[1，10，2]]

**方法 2:使用过滤器()+λ+min()+max()**

在本例中，我们使用 filter()和 lambda 执行过滤任务，rest min()和 max()用于获取极值差。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Filter rows with Extreme values greater than K
# Using filter() + lambda + min() + max()

# initializing list
test_list = [[3, 5, 1], [9, 1, 2], [3, 4, 2], [1, 10, 2]]

# printing original list
print("The original list is : " + str(test_list))

# initializing K 
K = 5

# max() and min() getting extreme difference
res = list(filter(lambda sub : max(sub) - min(sub) > K, test_list))

# printing result 
print("Filtered rows : " + str(res))
```

**输出:**

> 原始列表为:[[3，5，1]，[9，1，2]，[3，4，2]，[1，10，2]]
> 过滤行:[[9，1，2]，[1，10，2]]