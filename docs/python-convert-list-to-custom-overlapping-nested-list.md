# Python–将列表转换为自定义重叠嵌套列表

> 原文:[https://www . geesforgeks . org/python-convert-list-to-custom-重叠-嵌套-list/](https://www.geeksforgeeks.org/python-convert-list-to-custom-overlapping-nested-list/)

给定一个列表，任务是编写一个 Python 程序，根据元素大小和重叠步长将其转换为自定义的重叠嵌套列表。

**示例:**

> **输入:** test_list = [3，5，6，7，3，9，1，10]，步长，大小= 2，4
> 
> **输出:** [[3，5，6，7]，[6，7，3，9]，[3，9，1，10]，[1，10]]
> 
> **说明:**4 号切片的行，当前行 2 个元素后开始克服。
> 
> **输入:** test_list = [3，5，6，7，3，9，1，10]，步长，大小= 2，3
> 
> **输出:** [[3，5，6]，[6，7，3]，[3，9，1]，[1，10]]
> 
> **说明:**行被切成 3 号，当前行的 2 个元素后开始克服。

**方法#1:使用** [**列表切片**](https://www.geeksforgeeks.org/python-list-slicing/) **+** [**循环**](https://www.geeksforgeeks.org/loops-in-python/)

在这种情况下，行大小由切片操作管理，重叠步骤由 range()中提到的步骤管理，同时使用循环进行迭代。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Convert List to custom overlapping Matrix
# Using list slicing + loop

# initializing list
test_list = [3, 5, 6, 7, 3, 9, 1, 10]

# printing original list
print("The original list is : " + str(test_list))

# initializing step, size
step, size = 2, 4

res = []
for idx in range(0, len(test_list), step):

    # slicing list
    res.append(test_list[idx: idx + size])

# printing result
print("The created Matrix : " + str(res))
```

**输出:**

> 最初的名单是:[3、5、6、7、3、9、1、10]
> 
> 创建的矩阵:[[3，5，6，7]，[6，7，3，9]，[3，9，1，10]，[1，10]]

**方法二:使用** [**列表理解**](https://www.geeksforgeeks.org/python-list-comprehension/)

在这种情况下，与上述方法类似的功能被用于具有使用列表理解的速记的变体。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Convert List to custom overlapping Matrix
# Using list comprehension

# initializing list
test_list = [3, 5, 6, 7, 3, 9, 1, 10]

# printing original list
print("The original list is : " + str(test_list))

# initializing step, size
step, size = 2, 4

# list comprehension used as shorthand to solve problem
res = [test_list[idx: idx + size] for idx in range(0, 
                                                   len(test_list), 
                                                   step)]

# printing result
print("The created Matrix : " + str(res))
```

**输出:**

> 原来的名单是:[3，5，6，7，3，9，1，10]
> 
> 创建的矩阵:[[3，5，6，7]，[6，7，3，9]，[3，9，1，10]，[1，10]]