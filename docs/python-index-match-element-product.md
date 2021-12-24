# Python–索引匹配元素产品

> 原文:[https://www . geesforgeks . org/python-index-match-element-product/](https://www.geeksforgeeks.org/python-index-match-element-product/)

有时，在使用 Python 列表时，我们可能会遇到一个问题，即我们必须比较两个列表的索引相似性，因此可能会有一个乘法相等索引对的任务。让我们讨论一下执行这项任务的具体方法。

**方法#1:使用 loop + zip()**
该任务可以通过将执行将两个列表相互映射的任务的 zip()传递给根据相等索引计算乘积的函数来执行。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Index match element Product
# using loop + zip()

def prod(val) :    
    res = 1        
    for ele in list(val):        
        res *= ele        
    return res

# initialize lists
test_list1 = [5, 6, 10, 4, 7, 1, 19]
test_list2 = [6, 6, 10, 3, 7, 10, 19]

# printing original lists
print("The original list 1 is : " + str(test_list1))
print("The original list 2 is : " + str(test_list2))

# Index match element Product
# using loop + zip()
res = prod(x for x, y in zip(test_list1, test_list2) if x == y)

# printing result
print("Multiplication of Identical elements : " + str(res))
```

**Output : **

```
The original list 1 is : [5, 6, 10, 4, 7, 1, 19]
The original list 2 is : [6, 6, 10, 3, 7, 10, 19]
Multiplication of Identical elements : 7980
```