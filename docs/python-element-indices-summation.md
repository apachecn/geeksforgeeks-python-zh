# Python |元素指数求和

> 原文:[https://www . geesforgeks . org/python-element-indexs-summary/](https://www.geeksforgeeks.org/python-element-indices-summation/)

通常，我们要求找到特定值所在的索引的和。有许多方法可以实现这一点，使用 index()等。但有时需要找到一个特定值的所有索引，以防它在列表中多次出现。让我们讨论这样做的某些方法。

**方法#1:天真方法+ sum()**
我们可以通过遍历列表并检查该值来实现这个任务，只需在新列表中添加值索引并打印它。这是完成这个任务的基本蛮力方法。sum()用于执行列表求和。

```py
# Python code to demonstrate 
# Element indices Summation
# using naive method + sum()

# initializing list 
test_list = [1, 3, 4, 3, 6, 7]

# printing initial list 
print ("Original list : " + str(test_list))

# using naive method
# Element indices Summation
# to find indices for 3
res_list = []
for i in range(0, len(test_list)) :
    if test_list[i] == 3 :
        res_list.append(i)
res = sum(res_list)

# printing resultant list 
print ("New indices summation : " + str(res))
```

**Output :**

```py
Original list : [1, 3, 4, 3, 6, 7]
New indices summation : 4

```