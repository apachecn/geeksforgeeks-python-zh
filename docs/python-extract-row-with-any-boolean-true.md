# Python–提取任何布尔真值的行

> 原文:[https://www . geesforgeks . org/python-extract-row-with-any-boolean-true/](https://www.geeksforgeeks.org/python-extract-row-with-any-boolean-true/)

给定一个布尔矩阵，提取至少包含一个布尔真值的行。

> **输入** : test_list = [[False，False]，[True，True，True]，[False，True]，[False]]
> **输出** : [[True，True，True]，[False，True]]
> **解释**:提取至少 1 个 True 的所有行。
> 
> **输入** : test_list = [[False，False]，[False]]
> **输出** : []
> **解释**:无一行连一个 True。

**方法一:使用** [**列表理解**](https://www.geeksforgeeks.org/python-list-comprehension-and-slicing/) **+** [**任意()**](https://www.geeksforgeeks.org/any-all-in-python/)

在这种情况下，我们使用 any()检查任何元素是否为布尔真，列表理解用于矩阵中行的迭代任务。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Extract Row with any Boolean True
# Using list comprehension + any()

# initializing list
test_list = [[False, False], [True, True, True], [False, True], [False]]

# printing original list
print("The original list is : " + str(test_list))

# using any() to check for any True value 
res = [sub for sub in test_list if any(ele for ele in sub)]

# printing result 
print("Extracted Rows : " + str(res))
```

**输出:**

> 原始列表为:[[假，假]，[真，真，真]，[假，真]，[假]]提取的行:[[真，真，真]，[假，真]]

**方法 2:使用任意()+** [**滤镜()**](https://www.geeksforgeeks.org/filter-in-python/)**+**[**λ**](https://www.geeksforgeeks.org/python-lambda/)

在本例中，我们使用 any()和 filter()执行检查任何 True 值的任务，lambda 用于过滤掉匹配的行。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Extract Row with any Boolean True
# Using any() + filter() + lambda

# initializing list
test_list = [[False, False], [True, True, True], [False, True], [False]]

# printing original list
print("The original list is : " + str(test_list))

# using any() to check for any True value 
# filter() to perform filtering
res = list(filter(lambda sub : any(ele for ele in sub), test_list))

# printing result 
print("Extracted Rows : " + str(res))
```

**输出:**

> 原始列表为:[[假，假]，[真，真，真]，[假，真]，[假]]提取的行:[[真，真，真]，[假，真]]