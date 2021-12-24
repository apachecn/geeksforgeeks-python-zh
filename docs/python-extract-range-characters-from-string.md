# Python–从字符串中提取范围字符

> 原文:[https://www . geesforgeks . org/python-extract-range-characters-from-string/](https://www.geeksforgeeks.org/python-extract-range-characters-from-string/)

给定一个字符串，只提取位于给定字母之间的字符。

> **输入**:test _ str = ' geek forgek s best '，strt，end = ' g "，" s"
> **输出**:gkorgksis
> **解释**:保留 g 之后 s 之前的所有字符。
> 
> **输入**:test _ str = ' geek forgek s best '，strt，end = ' g "，" r"
> **输出** : gkorgki
> **解释**:保留 g 之后、r 之前的所有字符。

**方法一:使用列表理解**

在这种情况下，我们使用比较操作检查范围内的字符，列表理解执行迭代和创建新列表的任务。然后可以使用 join()重新转换为 string。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Extract range  characters from String
# Using list comprehension

# initializing string
test_str = 'geekforgeeks is best'

# printing original string
print("The original string is : " + str(test_str))

# initializing range letters 
strt, end = "f", "s"

# join() to get result in string 
res = ''.join([chr for chr in test_str if chr >= strt and chr <= end])

# printing result 
print("Extracted String : " + str(res)) 
```

**Output**

```py
The original string is : geekforgeeks is best
Extracted String : gkforgksiss

```

**方法 2:使用 filter() + lambda + join()**

解决这个问题的另一种方法是，我们使用 lambda 执行比较任务，filter()使用 lambda 函数获取所需的字符。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Extract range  characters from String
# Using filter() + lambda + join()

# initializing string
test_str = 'geekforgeeks is best'

# printing original string
print("The original string is : " + str(test_str))

# initializing range letters 
strt, end = "f", "s"

# join() to get result in string 
res = ''.join(list(filter(lambda chr : chr >= strt and chr <= end, test_str)))

# printing result 
print("Extracted String : " + str(res)) 
```

**Output**

```py
The original string is : geekforgeeks is best
Extracted String : gkforgksiss

```