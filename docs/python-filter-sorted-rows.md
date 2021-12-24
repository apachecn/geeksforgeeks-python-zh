# Python–过滤排序行

> 原文:[https://www.geeksforgeeks.org/python-filter-sorted-rows/](https://www.geeksforgeeks.org/python-filter-sorted-rows/)

给定矩阵，提取按升序或降序排序的行。

> **输入** : test_list = [[3，6，8，10]，[1，8，2，4，3]，[8，5，3，2]，[1，4，5，3]]
> **输出** : [[3，6，8，10]，[8，5，3，2]]
> **解释**:两个列表都是按顺序排列的，先升后降。
> 
> **输入** : test_list = [[3，6，8，10]，[1，8，2，4，3]，[8，5，7，2]，[1，4，5，3]]
> **输出** : [[3，6，8，10]]
> **解释**:列表按升序排列。

**方法一:使用** [**列表理解**](https://www.geeksforgeeks.org/python-list-comprehension-and-slicing/) **+** [**排序()**](https://www.geeksforgeeks.org/sorted-function-python/) **+反转**

在这种情况下，我们检查每一行，通过 sorted()执行排序，并通过传递 reverse 作为关键字进行反向排序。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Filter Sorted Rows
# Using list comprehension + sorted() + reverse

# initializing list
test_list = [[3, 6, 8, 10], [1, 8, 2, 4, 3], [8, 5, 3, 2], [1, 4, 5, 3]]

# printing original list
print("The original list is : " + str(test_list))

# filtering using sorted() and reverse as key
res = [sub for sub in test_list if sub == list(
    sorted(sub)) or sub == list(sorted(sub, reverse=True))]

# printing result
print("Extracted rows : " + str(res))
```

**输出:**

> 原始列表为:[[3，6，8，10]，[1，8，2，4，3]，[8，5，3，2]，[1，4，5，3]]
> 提取的行:[[3，6，8，10]，[8，5，3，2]]

**方法 2:使用** [**滤镜()**](https://www.geeksforgeeks.org/filter-in-python/)**+**[**lambda**](https://www.geeksforgeeks.org/python-lambda/)+sorted()+reverse

在这种情况下，我们使用 lambda 和 sorted()执行过滤任务，并且可以使用 reverse 来检查有序列表是否相等。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Filter Sorted Rows
# Using filter() + lambda + sorted() + reverse

# initializing list
test_list = [[3, 6, 8, 10], [1, 8, 2, 4, 3], [8, 5, 3, 2], [1, 4, 5, 3]]

# printing original list
print("The original list is : " + str(test_list))

# filtering using sorted() and reverse as key
res = list(filter(lambda sub: sub == list(sorted(sub)) or sub ==
                  list(sorted(sub, reverse=True)), test_list))

# printing result
print("Extracted rows : " + str(res))
```

**输出:**

> 原始列表为:[[3，6，8，10]，[1，8，2，4，3]，[8，5，3，2]，[1，4，5，3]]
> 提取的行:[[3，6，8，10]，[8，5，3，2]]