# Python–获取字符串列表中数字的总和

> 原文:[https://www . geesforgeks . org/python-get-summary-in-numbers-in-string-list/](https://www.geeksforgeeks.org/python-get-summation-of-numbers-in-string-list/)

有时，在处理数据时，我们可能会遇到一个问题，即我们接收到一系列字符串格式的数据列表，我们希望将其累积为列表。让我们讨论执行这项任务的某些方法。

**方法#1:使用 loop + `int()`**
这是执行这个任务的蛮力方法。在这种情况下，我们对整个列表运行一个循环，将每个字符串转换为整数，并按列表方式执行求和，然后存储在一个单独的列表中。

```py
# Python3 code to demonstrate working of
# Summation of String Integer lists
# using loop + int()

# initialize list 
test_list = [['1', '4'], ['5', '6'], ['7', '10']]

# printing original list 
print("The original list : " + str(test_list))

# Summation of String Integer lists
# using loop + int()
res = []
for sub in test_list:
    par_sum = 0
    for ele in sub:
        par_sum = par_sum + int(ele)
    res.append(par_sum)

# printing result
print("List after summation of nested string lists : " + str(res))
```

**Output :**

```py
The original list : [['1', '4'], ['5', '6'], ['7', '10']]
List after summation of nested string lists : [5, 11, 17]

```