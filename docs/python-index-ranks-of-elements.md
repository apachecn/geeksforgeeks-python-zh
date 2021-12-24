# Python–元素索引等级

> 原文:[https://www . geesforgeks . org/python-index-元素等级/](https://www.geeksforgeeks.org/python-index-ranks-of-elements/)

给定一个元素列表，我们的任务是获取每个元素的索引等级。

![Index Rank of Number = (Sum of occurrence indices of number) / number](img/229f3fbfd9802697a9df52144062cdaf.png "Rendered by QuickLaTeX.com")

> **输入:** test_list = [3，4，6，5，3，4，9，1，2，1，8，3，2，3，9]
> 
> **输出:** [(1，16.0)，(2，10.0)，(3，9.333333333334)，(4，1.5)，(5，0.6)，(6，0.3333333333333333)，(8，1.25)，(9，2.22222222222222222223)]
> 
> **说明:** 1 出现在索引 7 和 9 的列表中。9 + 7 = 16 / 1 = 16.
> 
> **输入:** test_list = [3，4，6，5，3，4，9，1，2，1，8，3，2，3，9]
> 
> **输出:** [(1，16.0)，(2，10.0)，(3，9.333333333334)，(4，1.5)，(5，0.6)，(6，0.3333333333333333)，(8，1.25)，(9，2.22222222222222222223)]
> 
> **说明:** 5 出现在指数 3。3 / 5 = 0.6.

**例:使用** [**循环**](https://www.geeksforgeeks.org/loops-in-python/) **+** [**过滤()**](https://www.geeksforgeeks.org/filter-in-python/) **+** [**列表理解**](https://www.geeksforgeeks.org/python-list-comprehension-and-slicing/) **+** [**集合()**](https://www.geeksforgeeks.org/python-set-method/)**+[**求和()**](https://www.geeksforgeeks.org/sum-function-python/)T30】+**[**循环**](https://www.geeksforgeeks.org/python-for-loops/)

在这种情况下，使用过滤器()和列表理解来提取元素的索引。set()用于获取列表中存在的唯一数字。sum()用于计算所有指数的总和。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Index Ranks of Elements
# Using loop + filter() + list comprehension. + set() + sum() + loop

# initializing list
test_list = [3, 4, 6, 5, 3, 4, 9,
             1, 2, 1, 8, 3, 2, 3, 9]

# printing original list
print("The original list is : " + str(test_list))

res = []
all_ele = set(test_list)
for ele in all_ele:

    # getting indices of each element 
    indices = list(filter(lambda sub: test_list[sub] == ele, range(len(test_list))))

    # index rank
    idx_rank = sum(indices) / ele
    res.append((ele, idx_rank))

# printing result
print("Index rank of each element : " + str(res))
```

**输出:**

> 原来的名单是:[3，4，6，5，3，4，9，1，2，1，8，3，2，3，9]
> 
> 各元素的指数排名:[(1，16.0)，(2，10.0)，(3，9.3333333333334)，(4，1.5)，(5，0.6)，(6，0.3333333333333333333)，(8，1.25)，(9，2.222222222222222222223)]