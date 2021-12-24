# Python |列表中的替代元素求和

> 原文:[https://www . geesforgeks . org/python-alternate-element-summary-in-list/](https://www.geeksforgeeks.org/python-alternate-element-summation-in-list/)

获得列表总和的问题是非常普遍的，我们可能有一天会面临获得替代元素总和的问题，并获得包含替代元素总和的 2 个元素的列表。让我们讨论一下实现这一点的某些方法。

**方法#1:使用列表理解+列表切片+ `sum()`**
使用列表理解的列表切片可以用来执行这个特定的任务。我们可以通过列表理解来得到运行逻辑，列表切片可以通过求和函数来切分出替换字符、求和

```py
# Python3 code to demonstrate
# alternate elements summation
# using list comprehension + list slicing

# initializing list 
test_list = [2, 1, 5, 6, 8, 10]

# printing original list 
print("The original list : " + str(test_list))

# using list comprehension + list slicing
# alternate elements summation
res = [sum(test_list[i : : 2])
      for i in range(len(test_list)//(len(test_list)//2))]

# print result
print("The alternate elements summation list : " + str(res))
```

**Output :**

```py
The original list : [2, 1, 5, 6, 8, 10]
The alternate elements summation list : [15, 17]

```