# Python |任意列表产品

> 原文:[https://www . geeksforgeeks . org/python-any-list-product/](https://www.geeksforgeeks.org/python-arbitrary-list-product/)

有时，在制作游戏或赌博程序时，我们会遇到用任意数字创建列表并执行其产品的任务。这个任务通常必须使用循环执行，将任意数字一个接一个地追加，然后执行乘积运算。但是总是要求以最简洁的方式执行此操作。让我们讨论一下实现这一点的某些方法。

**方法#1:使用列表理解+ `randrange()` +循环**
执行这个特定任务的幼稚方法可以使用列表理解来缩短。randrange 函数用于执行生成随机数的任务。执行产品的任务是使用循环完成的。

```
# Python3 code to demonstrate 
# Arbitrary List Product
# using list comprehension + randrange() + loop
import random

# getting Product 
def prod(val) : 
    res = 1 
    for ele in val: 
        res *= ele 
    return res  

# using list comprehension + randrange() + loop
# Arbitrary List Product
res = prod([random.randrange(1, 50, 1) for i in range(7)])

# printing result
print ("Arbitrary number product list is : " + str(res))
```

**Output :**

```
Arbitrary number product list is : 1182384000

```