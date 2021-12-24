# Python |列表调和平均值

> 原文:[https://www.geeksforgeeks.org/python-harmonic-mean-of-list/](https://www.geeksforgeeks.org/python-harmonic-mean-of-list/)

在使用 Python 时，我们可能会遇到一个问题，即我们需要找到一个累积列表的调和平均值。这个问题在数据科学领域很常见。让我们讨论一下解决这个问题的某些方法。

**方法#1:使用循环+公式**
处理这个问题的更简单的方式是使用计算调和平均值的公式，并使用循环短指针来执行。这是解决这个问题最基本的方法。

```
# Python3 code to demonstrate working of
# Harmonic Mean of List
# using loop + formula

# initialize list
test_list = [6, 7, 3, 9, 10, 15]

# printing original list
print("The original list is : " + str(test_list))

# Harmonic Mean of List
# using loop + formula
sum = 0
for ele in test_list:
    sum += 1 / ele    
res = len(test_list)/sum

# printing result
print("The harmonic mean of list is : " + str(res))
```

**Output :**

```
The original list is : [6, 7, 3, 9, 10, 15]
The harmonic mean of list is : 6.517241379310345

```