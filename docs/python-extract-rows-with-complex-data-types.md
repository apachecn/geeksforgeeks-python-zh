# Python–提取具有复杂数据类型的行

> 原文:[https://www . geesforgeks . org/python-extract-row-with-complex-data-type/](https://www.geeksforgeeks.org/python-extract-rows-with-complex-data-types/)

给定矩阵，提取具有复杂数据类型的行。

**示例:**

> **输入** : test_list = [[4，2，5]，[1，[3，4]，9]，[5]，[7，(2，3)，3，9]]
> **输出** : [[1，[3，4]，9]，[7，(2，3)，3，9]]
> **说明**:行分别有列表和元组。
> 
> **输入** : test_list = [[4，2，[5]]，[1，[3，4]，9]，[5]，[7，(2，3)，3，9]]
> **输出** : [[4，2，[5]]，[1，[3，4]，9]，[7，(2，3)，3，9]]
> **说明**:行分别有列表和元组。

**方法一:使用** [**列表理解**](https://www.geeksforgeeks.org/python-list-comprehension-and-slicing/)**+**[**is instance()**](https://www.geeksforgeeks.org/python-isinstance-method/)**+**[**any()**](https://www.geeksforgeeks.org/any-all-in-python/)

在这种情况下，我们使用 isinstance()检查行的每个元素是字典、元组、集合还是列表数据类型，如果发现任何元素具有该实例，则在结果中添加该行。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Extract rows with Complex data types
# Using list comprehension + isinstance() + any()

# initializing list
test_list = [[4, 2, 5], [1, [3, 4], 9], [5], [7, (2, 3), 3, 9]]

# printing original list
print("The original list is : " + str(test_list))

# checking for any of list, set, tuple or
# dictionary as complex structures
res = [row for row in test_list if any(isinstance(ele, list) or isinstance(ele, tuple)
                                       or isinstance(ele, dict) or isinstance(ele, set) for ele in row)]

# printing result
print("Filtered Rows : " + str(res))
```

**输出:**

> 原始列表为:[[4，2，5]，[1，[3，4]，9]，[5]，[7，(2，3)，3，9]]
> 筛选行:[[1，[3，4]，9]，[7，(2，3)，3，9]]

**方法 2:使用** [**滤镜()**](https://www.geeksforgeeks.org/filter-in-python/)**+**[**λ**](https://www.geeksforgeeks.org/python-lambda/)**+is instance()**

在本例中，我们使用 filter 和 lambda 执行过滤任务，使用 isinstance()检查数据类型。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Extract rows with Complex data types
# Using filter() + lambda + isinstance()

# initializing list
test_list = [[4, 2, 5], [1, [3, 4], 9], [5], [7, (2, 3), 3, 9]]

# printing original list
print("The original list is : " + str(test_list))

# checking for any of list, set, tuple or dictionary as complex structures
res = list(filter(lambda row: any(isinstance(ele, list) or isinstance(ele, tuple)
                                  or isinstance(ele, dict) or isinstance(ele, set) for ele in row), test_list))

# printing result
print("Filtered Rows : " + str(res))
```

**输出:**

> 原始列表为:[[4，2，5]，[1，[3，4]，9]，[5]，[7，(2，3)，3，9]]
> 筛选行:[[1，[3，4]，9]，[7，(2，3)，3，9]]