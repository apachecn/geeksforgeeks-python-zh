# Python–用所需元素过滤行

> 原文:[https://www . geesforgeks . org/python-filter-rows-with-required-elements/](https://www.geeksforgeeks.org/python-filter-rows-with-required-elements/)

给定一个矩阵，用其他列表中的必需元素过滤行。

> **输入** : test_list = [[2，4，6]，[7，4，3，2]，[2，4，8]，[1，1，9]]，check_list = [4，6，2，8]
> **输出** : [[2，4，6]，[2，4，8]]
> **说明**:所有元素均来自检查表。
> 
> **输入** : test_list = [[2，4，6]，[7，4，3，2]，[2，4，8]，[1，1，9]]，check_list = [6，2，8]
> **输出** : []
> **解释**:没有包含检查表中所有元素的列表。

**方法一:使用** [**列表理解**](https://www.geeksforgeeks.org/python-list-comprehension-and-slicing/) **+** [**全部()**](https://www.geeksforgeeks.org/any-all-in-python/)

在本例中，我们使用列表中的列表理解执行迭代和过滤，并使用 all()检查每行中存在的所有元素。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Filter rows with required elements
# Using list comprehension + all()

# initializing list
test_list = [[2, 4, 6], [7, 4, 3, 2], [2, 4, 8], [1, 1, 9]]

# printing original list
print("The original list is : " + str(test_list))

# initializing check_list
check_list = [4, 6, 2, 8]

# using in operator to check for presence
res = [sub for sub in test_list if all(ele in check_list for ele in sub)]

# printing result
print("Filtered rows : " + str(res))
```

**输出:**

> 原始列表为:[[2，4，6]，[7，4，3，2]，[2，4，8]，[1，1，9]]
> 过滤行:[[2，4，6]，[2，4，8]]

**方法 2:使用** [**滤镜()**](https://www.geeksforgeeks.org/filter-in-python/)**+**[**λ**](https://www.geeksforgeeks.org/python-lambda/)**+all()**

在这种情况下，使用 filter()和 lambda 完成过滤任务，all()用于从清单中提取所有元素。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Filter rows with required elements
# Using filter() + lambda + all()

# initializing list
test_list = [[2, 4, 6], [7, 4, 3, 2], [2, 4, 8], [1, 1, 9]]

# printing original list
print("The original list is : " + str(test_list))

# initializing check_list 
check_list = [4, 6, 2, 8]

# using in operator to check for presence
# filter(), getting all rows checking from check_list
res = list(filter(lambda sub : all(ele in check_list for ele in sub), test_list))

# printing result 
print("Filtered rows : " + str(res))
```

**输出:**

> 原始列表为:[[2，4，6]，[7，4，3，2]，[2，4，8]，[1，1，9]]
> 过滤行:[[2，4，6]，[2，4，8]]