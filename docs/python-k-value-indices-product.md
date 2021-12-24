# Python | K 值指数产品

> 原文:[https://www . geesforgeks . org/python-k-value-indexs-product/](https://www.geeksforgeeks.org/python-k-value-indices-product/)

通常，我们需要找到特定值所在的索引。有许多方法可以实现这一点，使用 index()等。但是有时需要找到一个特定值的所有索引，以防它在列表中多次出现并计算它们的乘积。让我们讨论这样做的某些方法。

**方法#1:天真的方法**
我们可以通过遍历列表并检查该值来实现这个任务，只需在新列表中添加值索引并打印它。这是完成这个任务的基本蛮力方法。执行产品的任务是通过循环完成的。

```
# Python code to demonstrate 
# K Value Indices Product
# using naive method 

# initializing list 
test_list = [1, 3, 4, 3, 6, 7, 3]

# printing initial list 
print ("Original list : " + str(test_list))

# initializing K 
K = 3

# using naive method
# K Value Indices Product
res = 1
for i in range(0, len(test_list)) :
    if test_list[i] == K :
        res *= i

# printing resultant list 
print ("K Value indices product is : " + str(res))
```

**Output :**

```
Original list : [1, 3, 4, 3, 6, 7, 3]
K Value indices product is : 18

```