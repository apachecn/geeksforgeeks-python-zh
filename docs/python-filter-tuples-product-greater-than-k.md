# Python–过滤乘积大于 K 的元组

> 原文:[https://www . geesforgeks . org/python-filter-元组-product-大于-k/](https://www.geeksforgeeks.org/python-filter-tuples-product-greater-than-k/)

给定一个元组列表，提取乘积大于 k 的所有元组

> **输入** : test_list = [(4，5，7)，(1，2，3)，(8，4，2)，(2，3，4)]，K = 50
> **输出** : [(4，5，7)，(8，4，2)]
> **解释** : 140 和 64 大于 50，因此提取元组。
> 
> **输入** : test_list = [(4，5，7)，(1，2，3)，(8，4，2)，(2，3，4)]，K = 100
> **输出** : [(4，5，7)]
> **解释** : 140 大于 100，因此提取元组。

**方法一:使用列表理解**

在这种情况下，我们提取所有元组，大于 K 的乘积使用外部函数。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Filter Tuples Product greater than K
# Using list comprehension

# getting product
def prod(box):
    res = 1
    for ele in box:
        res *= ele
    return res

# initializing list
test_list = [(4, 5, 7), (1, 2, 3), (8, 4, 2), (2, 3, 4)]

# printing original list
print("The original list is : " + str(test_list))

# initializing K
K = 50

res = [sub for sub in test_list if prod(sub) > K]

# printing result
print("Tuples with product greater than K : " + str(res))
```

**输出:**

> 原列表为:[(4，5，7)，(1，2，3)，(8，4，2)，(2，3，4)]
> 乘积大于 K 的元组:[(4，5，7)，(8，4，2)]

**方法 2:使用过滤器()+λ**

在这种情况下，过滤元组的任务使用*过滤器()*和*λ*来完成，乘积以类似的方式计算。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Filter Tuples Product greater than K
# Using filter() + lambda

# getting product 
def prod(box):
    res = 1
    for ele in box:
        res *= ele 
    return res 

# initializing list
test_list = [(4, 5, 7), (1, 2, 3), (8, 4, 2), (2, 3, 4)]

# printing original list
print("The original list is : " + str(test_list))

# initializing K 
K = 50 

# using filter() to get products greater than K
res = list(filter(lambda sub : prod(sub) > K, test_list))

# printing result 
print("Tuples with product greater than K : " + str(res))
```

**输出:**

> 原列表为:[(4，5，7)，(1，2，3)，(8，4，2)，(2，3，4)]
> 乘积大于 K 的元组:[(4，5，7)，(8，4，2)]