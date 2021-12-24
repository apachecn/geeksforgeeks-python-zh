# Python–使用范围元素过滤行

> 原文:[https://www . geesforgeks . org/python-filter-row-with-range-elements/](https://www.geeksforgeeks.org/python-filter-rows-with-range-elements/)

给定一个矩阵，过滤包含给定数字范围内所有元素的所有行。

> **输入** : test_list = [[3，2，4，5，10]，[3，2，5，19]，[2，5，10]，[2，3，4，5，6，7]]，I，j = 2，5
> **输出** : [[3，2，4，5，10]，[2，3，4，5，6，7]]
> **解释** : 2，3，4，5 都在上面
> 
> **输入** : test_list = [[3，2，4，10]，[3，2，5，19]，[2，5，10]，[2，3，4，5，6，7]]，I，j = 2，5
> **输出** : [[2，3，4，5，6，7]]
> **解释** : 2，3，4，5 全部出现在以上行。

**方法#1:使用**[**all()**](https://www.geeksforgeeks.org/any-all-in-python/)**+**[**列表理解**](https://www.geeksforgeeks.org/python-list-comprehension-and-slicing/)

在这种情况下，我们使用 all()检查范围内的所有元素是否存在，列表理解用于元素迭代的任务。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Filter Rows with Range Elements
# Using all() + list comprehension

# initializing list
test_list = [[3, 2, 4, 5, 10], [3, 2, 5, 19], 
             [2, 5, 10], [2, 3, 4, 5, 6, 7]]

# printing original list
print("The original list is : " + str(test_list))

# initializing range
i, j = 2, 5

# checking for presence of all elements using in operator
res = [sub for sub in test_list if all(ele in sub for ele in range(i, j + 1))]

# printing result
print("Extracted rows : " + str(res))
```

**输出:**

> 原始列表为:[[3，2，4，5，10]，[3，2，5，19]，[2，5，10]，[2，3，4，5，6，7]]
> 提取的行:[[3，2，4，5，10]，[2，3，4，5，6，7]]

**方法 2:使用** [**滤镜()**](https://www.geeksforgeeks.org/filter-in-python/)**+**[**λ**](https://www.geeksforgeeks.org/python-lambda/)**+all()**

在这种情况下，使用 filter()和 lambda 函数完成过滤任务，再次使用 all()来确保范围内的所有元素都存在。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Filter Rows with Range Elements
# Using filter() + lambda + all()

# initializing list
test_list = [[3, 2, 4, 5, 10], [3, 2, 5, 19],
             [2, 5, 10], [2, 3, 4, 5, 6, 7]]

# printing original list
print("The original list is : " + str(test_list))

# initializing range
i, j = 2, 5

# filter() and lambda used to filter elements
res = list(filter(lambda sub: all(
    ele in sub for ele in range(i, j + 1)), test_list))

# printing result
print("Extracted rows : " + str(res))
```

**输出:**

> 原始列表为:[[3，2，4，5，10]，[3，2，5，19]，[2，5，10]，[2，3，4，5，6，7]]
> 提取的行:[[3，2，4，5，10]，[2，3，4，5，6，7]]