# Python–列表中直到当前索引的元素最大值

> 原文:[https://www . geesforgeks . org/python-elements-maximum-til-current-index-in-list/](https://www.geeksforgeeks.org/python-elements-maximum-till-current-index-in-list/)

给定包含元素的列表，如果元素是当前索引前的最大元素，则提取该元素。

> **输入** : test_list = [4，6，7，8]
> 
> **输出**:【4，6，7，8】
> 
> **说明**:所有元素都是最大值，直到它们的索引。
> 
> **输入** : test_list = [6，7，3，6，8，7]
> 
> **输出**:【7，8】
> 
> **说明** : 7 和 8 最大，直到它们的指数。

**方法#1:使用循环**

这是一种可以执行这项任务的暴力方法。在这种情况下，我们运行嵌套循环直到当前索引，如果所有元素都低于当前元素，则递增计数器，如果计数器匹配当前索引，则建议当前元素最大直到当前索引。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Elements Maximum till current index in List
# Using loop

# initializing list
test_list = [3, 5, 2, 6, 7, 9, 3]

# printing original list
print("The original list : " + str(test_list))

# Using loop
res = []
for idx in range(1, len(test_list)):
    cnt = 0

    # inner loop to count element less than current
    for idx2 in range(idx):
        if test_list[idx] > test_list[idx2]:
            cnt = cnt + 1
    if cnt == idx:
        res.append(test_list[idx])

# printing result
print("Extracted Maximum elements : " + str(res))
```

**Output**

```py
The original list : [3, 5, 2, 6, 7, 9, 3]
Extracted Maximum elements : [5, 6, 7, 9]

```

**方法二:使用 max() +列表理解+列表切片**

上述功能的组合可以用来解决这个问题。在这种情况下，我们使用 max()检查当前元素是否大于使用列表切片提取的所有先前元素。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Elements Maximum till current index in List
# Using max() + list comprehension + list slicing

# initializing list
test_list = [3, 5, 2, 6, 7, 9, 3]

# printing original list
print("The original list : " + str(test_list))

# Using max() + list comprehension + list slicing
# max() used to get if current is current maximum
res = [test_list[idx] for idx in range(
    1, len(test_list)) if test_list[idx] > max(test_list[:idx])]

# printing result
print("Extracted Maximum elements : " + str(res))
```

**Output**

```py
The original list : [3, 5, 2, 6, 7, 9, 3]
Extracted Maximum elements : [5, 6, 7, 9]

```