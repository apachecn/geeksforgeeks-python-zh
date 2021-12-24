# Python–提取特定数据类型行

> 原文:[https://www . geesforgeks . org/python-extract-special-data-type-row/](https://www.geeksforgeeks.org/python-extract-particular-data-type-rows/)

给定一个矩阵，提取具有特定数据类型的所有元素的所有行。

> **输入** : test_list = [[4，5，【Hello】，[2，6，7]，[“g”，“f”，“g”]，[9，10，11]]，data_type = int
> **输出** : [[2，6，7]，[9，10，11]]
> **说明:**提取所有带整数的列表。
> 
> **输入** : test_list = [[4，5，“Hello”]，[2，6，7]，[“g”，“f”，“g”]，[9，10，11]]，data_type = str
> **输出**:[“g”，“f”，“g”]
> **解释**:提取所有带字符串的列表。

**方法一:使用 isinstance() + all() +列表理解**

在本例中，我们使用 *isinstance()检查数据类型，all()* 检查特定数据类型的所有元素。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Extract Particular data type rows
# Using isinstance() + all() + list comprehension

# initializing list
test_list = [[4, 5, "Hello"], [2, 6, 7], ["g", "f", "g"], [9, 10, 11]]

# printing original list
print("The original list is : " + str(test_list))

# initializing data type
data_type = int

# checking data type using isinstance
res = [row for row in test_list if all(
    isinstance(ele, data_type) for ele in row)]

# printing result
print("Filtered Rows : " + str(res))
```

**输出:**

> 原始列表为:[[4，5，' Hello']，[2，6，7]，['g '，' f '，' g']，[9，10，11]]
> 过滤行:[[2，6，7]，[9，10，11]]

**方法 2:使用滤镜()+ lambda + isinstance()**

在本例中，我们使用 *filter()* 和 *lambda 执行过滤任务，isinstance()* 用于执行与上述方法相同的类型检查任务。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Extract Particular data type rows
# Using filter() + lambda + isinstance()

# initializing list
test_list = [[4, 5, "Hello"], [2, 6, 7], ["g", "f", "g"], [9, 10, 11]]

# printing original list
print("The original list is : " + str(test_list))

# initializing data type
data_type = int

# checking data type using isinstance
# filter() used to get filter
res = list(filter(lambda row: all(isinstance(ele, data_type)
                                  for ele in row), test_list))

# printing result
print("Filtered Rows : " + str(res))
```

**输出:**

> 原始列表为:[[4，5，' Hello']，[2，6，7]，['g '，' f '，' g']，[9，10，11]]
> 过滤行:[[2，6，7]，[9，10，11]]