# Python–逐行连接两个列表

> 原文:[https://www . geeksforgeeks . org/python-concatenate-双列表-逐行/](https://www.geeksforgeeks.org/python-concatenate-two-list-of-lists-row-wise/)

给定两个矩阵，任务是编写一个 Python 程序，从初始矩阵向每行添加元素。

> **输入:** test_list1 = [[4，3，5，]，[1，2，3]，[3，7，4]]，test_list2 = [[1，3]，[9，3，5，7]，[8]]
> 
> **输出:** [[4，3，5，1，3]，[1，2，3，9，3，5，7]，[3，7，4，8]]
> 
> **说明:**矩阵逐行合并。
> 
> **输入:** test_list1 = [[4，3，5，]，[1，2，3]，[3，7，4]]，test_list2 = [[1]，[9]，[8]]
> 
> **输出:** [[4，3，5，1]，[1，2，3，9]，[3，7，4，8]]
> 
> **说明:**矩阵逐行合并。

**方法#1:使用** [**枚举()**](https://www.geeksforgeeks.org/enumerate-in-python/) **+** [**循环**](https://www.geeksforgeeks.org/loops-in-python/)

在这种情况下，我们得到每个初始矩阵的每个索引，并将其所有元素附加到第二个矩阵的相应行。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Concatenate 2 Matrix Row-wise
# Using loop + enumerate()

# initializing lists
test_list1 = [[4, 3, 5, ], [1, 2, 3], [3, 7, 4]]
test_list2 = [[1, 3], [9, 3, 5, 7], [8]]

# printing original lists
print("The original list 1 is : " + str(test_list1))
print("The original list 2 is : " + str(test_list2))

for idx, ele in enumerate(test_list1):
    new_vals = []

    # getting all values at same index row
    for ele in test_list2[idx]:
        new_vals.append(ele)

    # extending the initial matrix
    test_list1[idx].extend(new_vals)

# printing result
print("The concatenated Matrix : " + str(test_list1))
```

**输出:**

> 原始列表 1 是:[[4，3，5]，[1，2，3]，[3，7，4]]
> 
> 原始列表 2 是:[[1，3]，[9，3，5，7]，[8]]
> 
> 串联矩阵:[[4，3，5，1，3]，[1，2，3，9，3，5，7]，[3，7，4，8]]

**方法二:使用**[**zip()**](https://www.geeksforgeeks.org/zip-in-python/)**+**[**列表理解**](https://www.geeksforgeeks.org/python-list-comprehension/)

在本例中，我们使用 zip()执行连接行的任务，并使用列表理解对每一行进行迭代。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Concatenate 2 Matrix Row-wise
# Using zip() + list comprehension

# initializing lists
test_list1 = [[4, 3, 5, ], [1, 2, 3], [3, 7, 4]]
test_list2 = [[1, 3], [9, 3, 5, 7], [8]]

# printing original lists
print("The original list 1 is : " + str(test_list1))
print("The original list 2 is : " + str(test_list2))

# zip() combines the results
# list comprehension provides shorthand
res = list(sub1 + sub2 for sub1, sub2 in zip(test_list1, test_list2))

# printing result
print("The concatenated Matrix : " + str(res))
```

**输出:**

> 原始列表 1 是:[[4，3，5]，[1，2，3]，[3，7，4]]
> 
> 原始列表 2 是:[[1，3]，[9，3，5，7]，[8]]
> 
> 串联矩阵:[[4，3，5，1，3]，[1，2，3，9，3，5，7]，[3，7，4，8]]