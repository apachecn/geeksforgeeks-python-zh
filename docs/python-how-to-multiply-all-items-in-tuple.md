# Python–如何将元组

中的所有项目相乘

> 原文:[https://www . geesforgeks . org/python-如何将元组中的所有项相乘/](https://www.geeksforgeeks.org/python-how-to-multiply-all-items-in-tuple/)

有时候，在编程时，我们会遇到一个问题，那就是我们可能需要在元组元素之间执行乘积运算。这是一个必不可少的工具，因为我们多次遇到产品操作，元组是不可变的，因此需要处理。让我们讨论执行这项任务的某些方法。

**方法#1:使用`list()` +循环**
以上功能可以组合执行此任务。我们可以使用循环来累加乘积逻辑的结果。list()函数用于执行相互转换。

```
# Python3 code to demonstrate working of 
# Tuple Elements Multiplication
# Using list() + loop

# getting Product 
def prod(val) : 
    res = 1 
    for ele in val: 
        res *= ele 
    return res  

# initializing tup 
test_tup = (7, 8, 9, 1, 10, 7) 

# printing original tuple 
print("The original tuple is : " + str(test_tup)) 

# Tuple Elements Multiplication 
# Using list() + loop
res = prod(list(test_tup)) 

# printing result 
print("The product of tuple elements are : " + str(res)) 
```

**Output :**

```
The original tuple is : (7, 8, 9, 1, 10, 7)
The product of tuple elements are : 35280

```