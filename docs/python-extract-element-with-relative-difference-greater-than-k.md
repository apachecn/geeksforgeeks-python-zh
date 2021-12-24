# Python–提取相对差值大于 K 的元素

> 原文:[https://www . geesforgeks . org/python-extract-element-with-relative-difference-behind-k/](https://www.geeksforgeeks.org/python-extract-element-with-relative-difference-greater-than-k/)

给定一个数字列表，任务是编写一个 Python 程序来提取当前元素大于 k 的下一个和上一个元素的差异的所有数字。

> **输入:** test_list = [2，7，4，1，9，2，3，10，1，5]，K = 4
> 
> **输出:**【9，10】
> 
> **说明:** 9 有 1 作为前置元素，2 作为后置元素。8 和 7 分别是大于 4 的差值。
> 
> **输入:** test_list = [2，7，4，1，9，2]，K = 4
> 
> **输出:**【9】
> 
> **说明:** 9 有 1 作为前置元素，2 作为后置元素。8 和 7 分别是大于 4 的差值。

**方法#1:使用** [**循环**](https://www.geeksforgeeks.org/loops-in-python/)

在这种情况下，我们使用蛮力检查下一个或上一个元素是否有小于 K 的元素差，并省略它们。循环用于所有元素的迭代。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Extract element with relative difference 
# greater than K Using loop

# initializing list
test_list = [2, 7, 4, 1, 9, 2, 3, 10, 1, 5]

# printing original list
print("The original list is : " + str(test_list))

# initializing K
K = 4

res = []
for idx in range(1, len(test_list)):

    # using abs to get absolute difference
    if abs(test_list[idx - 1] - test_list[idx]) > K\
            and abs(test_list[idx + 1] - test_list[idx]) > K:
        res.append(test_list[idx])

# printing result
print("The extracted difference elements : " + str(res))
```

**输出:**

```py
The original list is : [2, 7, 4, 1, 9, 2, 3, 10, 1, 5]
The extracted difference elements : [9, 10]
```

**方法二:使用** [**列表理解**](https://www.geeksforgeeks.org/python-list-comprehension/)

这类似于上面的方法，不同的只是使用列表理解来简化问题的解决。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Extract element with relative difference
# greater than K Using list comprehension

# initializing list
test_list = [2, 7, 4, 1, 9, 2, 3, 10, 1, 5]

# printing original list
print("The original list is : " + str(test_list))

# initializing K
K = 4

# using abs to get absolute difference
# list comprehension provides shorthand
res = [test_list[idx] for idx in range(
  1, len(test_list)) if abs(test_list[idx - 1] - test_list[idx]) > K
       and abs(test_list[idx + 1] - test_list[idx]) > K]

# printing result
print("The extracted difference elements : " + str(res))
```

**输出:**

```py
The original list is : [2, 7, 4, 1, 9, 2, 3, 10, 1, 5]
The extracted difference elements : [9, 10]
```