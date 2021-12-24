# 在 Python 中将字符串浮点转换为浮点列表

> 原文:[https://www . geesforgeks . org/convert-string-float-to-float-list-in-python/](https://www.geeksforgeeks.org/convert-string-float-to-float-list-in-python/)

有时，在处理数据时，我们可能会处理十进制而非整数的数字。这是数据科学领域的一般情况。让我们讨论如何解决一个问题，其中我们可能有一个逗号分隔的浮点数，我们需要转换为浮点列表。

**方法#1:使用列表理解+拆分()+浮动()**
以上方法的组合可以用来执行这个任务。在本文中，我们使用 split 将字符串转换为字符串列表，然后使用 float()将字符串转换为 float。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Convert String float to float list
# using list comprehension + split() + float()

# initializing string
test_str = "3.44, 7.8, 9.12, 100.2, 6.50"

# printing original string
print("The original string is : " + test_str)

# Convert String float to float list
# using list comprehension + split() + float()
res = [float(idx) for idx in test_str.split(', ')]

# printing result
print("The float list is : " + str(res))
```

**Output : **

```py
The original string is : 3.44, 7.8, 9.12, 100.2, 6.50
The float list is : [3.44, 7.8, 9.12, 100.2, 6.5]
```

**方法 2:使用 map() + split() + float()**
以上功能的组合也可以用来解决这个问题。在这种情况下，我们使用 map()执行将逻辑扩展到整个列表的任务，其余所有功能都按照上述方法执行。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Convert String float to float list
# using map() + split() + float()

# initializing string
test_str = "3.44, 7.8, 9.12, 100.2, 6.50"

# printing original string
print("The original string is : " + test_str)

# Convert String float to float list
# using map() + split() + float()
res = list(map(float, test_str.split(', ')))

# printing result
print("The float list is : " + str(res))
```

**Output : **

```py
The original string is : 3.44, 7.8, 9.12, 100.2, 6.50
The float list is : [3.44, 7.8, 9.12, 100.2, 6.5]
```