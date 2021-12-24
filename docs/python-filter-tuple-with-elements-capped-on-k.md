# Python–过滤元素以 K 为上限的元组

> 原文:[https://www . geesforgeks . org/python-filter-tuple-with-elements-capped-on-k/](https://www.geeksforgeeks.org/python-filter-tuple-with-elements-capped-on-k/)

给定元组列表，提取每个元素都是最大 k 的元组

> **输入** : test_list = [(4，5，3)，(3，4，7)，(4，3，2)，(4，7，8)]，K = 7
> **输出** : [(4，5，3)，(3，4，7)，(4，3，2)]
> **解释**:所有元组最大值为 7。
> 
> **输入** : test_list = [(4，5，3)，(4，3，2)，(4，7，8)]，K = 7
> **输出** : [(4，5，3)，(4，3，2)]
> **解释**:所有元组都有最大值 7。

**方法#1:使用循环**

在这种情况下，我们遍历所有元组元素，如果发现元素大于 K，那么元组被标记，而不添加到结果列表中。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Filter Tuple with Elements capped on K
# Using loop

# initializing list
test_list = [(4, 5, 3), (3, 4, 7), (4, 3, 2), (4, 7, 8)]

# printing original list
print("The original list is : " + str(test_list))

# initializing K
K = 5

res_list = []
for sub in test_list:
    res = True 
    for ele in sub:

        # check if any element is greater than K
        if ele > K :
            res = False 
            break
    if res:
        res_list.append(sub)

# printing result 
print("The filtered tuples : " + str(res_list))
```

**Output**

```py
The original list is : [(4, 5, 3), (3, 4, 7), (4, 3, 2), (4, 7, 8)]
The filtered tuples : [(4, 5, 3), (4, 3, 2)]

```

**方法 2:使用 all() +列表理解**

在这种情况下，我们使用 all()检查所有元素是否都在最大 K，如果是，则将这些元组添加到结果中。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Filter Tuple with Elements capped on K
# Using all() + list comprehension

# initializing list
test_list = [(4, 5, 3), (3, 4, 7), (4, 3, 2), (4, 7, 8)]

# printing original list
print("The original list is : " + str(test_list))

# initializing K
K = 5

# using all() to check for each tuple being in K limit
res = [sub for sub in test_list if all(ele <= K for ele in sub)]

# printing result 
print("The filtered tuples : " + str(res))
```

**Output**

```py
The original list is : [(4, 5, 3), (3, 4, 7), (4, 3, 2), (4, 7, 8)]
The filtered tuples : [(4, 5, 3), (4, 3, 2)]

```