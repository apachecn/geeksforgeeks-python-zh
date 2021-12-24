# Python |列表列表中的列产品

> 原文:[https://www . geesforgeks . org/python-column-产品列表中的产品/](https://www.geeksforgeeks.org/python-column-product-in-list-of-lists/)

有时，我们会遇到这样的问题，我们需要找到矩阵中每一列的乘积，即列表中每个索引的乘积。这种问题在竞争性编程中很常见，也很有用。让我们讨论一下解决这个问题的某些方法。

**方法#1:使用循环+列表理解+ `zip()`**
需要结合以上方法来解决这个特定的问题。显式产品函数用于获取所需的产品值，zip 函数提供相似索引的组合，然后使用列表理解创建列表。

```py
# Python3 code to demonstrate
# Column Product in List of lists
# using loop + list comprehension + zip()

# getting Product
def prod(val) :
    res = 1 
    for ele in val:
        res *= ele
    return res 

# initializing list
test_list = [[3, 7, 6], [1, 3, 5], [9, 3, 2]]

# printing original list
print("The original list : " + str(test_list))

# using loop + list comprehension + zip()
# Column Product in List of lists
res = [prod(idx) for idx in zip(*test_list)]

# print result
print("The Product of each index list is : " + str(res))
```

**Output :**

```py
The original list : [[3, 7, 6], [1, 3, 5], [9, 3, 2]]
The Product of each index list is : [27, 63, 60]

```