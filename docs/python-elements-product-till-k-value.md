# Python–元素积至 K 值

> 原文:[https://www . geesforgeks . org/python-elements-product-till-k-value/](https://www.geeksforgeeks.org/python-elements-product-till-k-value/)

其中一个问题基本上是许多复杂问题的子问题，在 python 中找到产品编号，直到列表中的某个编号，这是经常遇到的问题，本文将讨论这个特定问题的可能解决方案。

**方法#1:天真的方法**
解决这个问题最常见的方法是使用一个循环，并将元素的出现次数相乘，直到给定的数字为 k

```
# Python 3 code to demonstrate 
# Elements Product till K value
# using naive method 

# initializing list 
test_list = [1, 7, 5, 6, 3, 8] 

# initializing k 
k = 6

# printing list 
print ("The list : " + str(test_list)) 

# using naive method 
# Elements Product till K value
res = 1
for i in test_list : 
    if i <= k : 
        res *= i 

# printing the product
print ("The product till K : " + str(res)) 
```

**Output :**

```
The list : [1, 7, 5, 6, 3, 8]
The product till K : 90

```