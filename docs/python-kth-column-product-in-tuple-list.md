# Python–元组列表中的第 k 列乘积

> 原文:[https://www . geesforgeks . org/python-kth-column-product-in-tuple-list/](https://www.geeksforgeeks.org/python-kth-column-product-in-tuple-list/)

有时，在使用 Python 列表时，我们可能会有一个任务，其中我们需要使用元组列表并获取其 Kth 索引的乘积。当处理数据信息时，这个问题在 web 开发领域有应用。让我们讨论执行这项任务的某些方法。

**方法#1:使用列表理解+循环**
该任务可以使用上述功能的组合来执行。在这种情况下，使用显式乘积函数进行索引乘积，列表理解驱动列表中每个元组的 Kth 索引元素的迭代和访问。

```py
# Python3 code to demonstrate working of
# Tuple List Kth Column Product
# using list comprehension + loop

# getting Product
def prod(val) :
    res = 1 
    for ele in val:
        res *= ele
    return res 

# initialize list
test_list = [(5, 6, 7), (1, 3, 5), (8, 9, 19)]

# printing original list
print("The original list is : " + str(test_list))

# initialize K
K = 2

# Tuple List Kth Column Product
# using list comprehension + loop
res = prod([sub[K] for sub in test_list])

# printing result
print("Product of Kth Column of Tuple List : " + str(res))
```

**Output :**

```py
The original list is : [(5, 6, 7), (1, 3, 5), (8, 9, 19)]
Product of Kth Column of Tuple List : 665

```