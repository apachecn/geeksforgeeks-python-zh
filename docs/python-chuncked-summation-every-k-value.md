# Python |每 K 个值的 Chuncked 求和

> 原文:[https://www . geesforgeks . org/python-chunk-summary-ever-k-value/](https://www.geeksforgeeks.org/python-chuncked-summation-every-k-value/)

前缀数组在编程界相当有名。本文将讨论这个方案的一个变体。这将处理累积的列表总和直到一个 K 值，并且再次从 K 值的出现开始总和的累积。让我们讨论一下实现这一点的特定方式。

**方法#1:使用天真的方法**
在天真的方法中，我们只需构建包含前一个的和的新列表。列表的值，直到 K，并在遇到非 K 值时重新启动程序。

```
# Python3 code to demonstrate 
# Chuncked summation every K value
# using naive method 

# initializing list of lists
test_list = [1, 3, 4, 10, 4, 5, 10, 7, 8]

# printing original list
print ("The original list is : " + str(test_list))

# initializing K 
K = 10

# Chuncked summation every K value
# using naive method
for i in range(1, len(test_list)):
    if test_list[i]: 
        test_list[i] += test_list[i - 1]
    else:
        test_list[i] = 0

# printing result
print ("The computed modified new list : " + str(test_list))
```

**Output :**

```
The original list is : [1, 3, 4, 10, 4, 5, 10, 7, 8]
The computed modified new list : [1, 4, 8, 18, 22, 27, 37, 44, 52]

```