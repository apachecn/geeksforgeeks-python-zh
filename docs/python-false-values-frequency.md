# Python–错误值频率

> 原文:[https://www . geesforgeks . org/python-false-values-frequency/](https://www.geeksforgeeks.org/python-false-values-frequency/)

按条件检查数字/元素是一个人面临的常见问题，几乎在每个程序中都要做。有时，我们还需要获得与特定条件匹配的总数，以区分哪些不匹配，以便进一步利用，如在数据科学中。让我们讨论一下计算假值的某些方法。

**方法#1:使用`sum()` +生成器表达式**
每当生成器表达式返回 true 时，该方法就使用总和加 1 的技巧。当列表耗尽时，返回与条件匹配的数字总数。

```py
# Python 3 code to demonstrate 
# False values Frequency
# using sum() + generator expression 

# initializing list 
test_list = [3, False, False, 6, False, 9] 

# printing original list 
print ("The original list is : " + str(test_list)) 

# using sum() + generator expression 
# False values Frequency
# checks for False
res = sum(1 for i in test_list if not i) 

# printing result 
print ("The number of False elements: " + str(res)) 
```

**Output :**

```py
The original list is : [3, False, False, 6, False, 9]
The number of False elements: 3

```