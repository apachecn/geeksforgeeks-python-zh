# Python |二元组元组列表元素

> 原文:[https://www . geesforgeks . org/python-二进制-组-元组-列表-元素/](https://www.geeksforgeeks.org/python-binary-group-tuple-list-elements/)

有时，在处理元组时，我们可能会遇到分组问题，无论是基于性别还是任何特定的二元类别。这在许多领域都有应用。让我们讨论一下实现这一点的某些方法。

**方法#1:使用【生成器+循环+ `zip()`**
的蛮力方法执行此任务，在此，我们借助`zip()`执行组合分组，迭代逻辑由生成器和循环处理。

```py
# Python3 code to demonstrate working of
# Binary Group Tuple list elements
# using generator + loop + zip()

# helper function to perform task 
def bin_group(test_list):
     for tup1, tup2 in zip(test_list[0::2], test_list[1::2]):
             yield (tup1[0], tup1[1], tup2[1])

# initialize list 
test_list = [(1, 56, 'M'), (1, 14, 'F'), (2, 43, 'F'), (2, 10, 'M')]

# printing original list 
print("The original list : " + str(test_list))

# Binary Group Tuple list elements
# using generator + loop + zip()
res = list(bin_group(test_list))

# printing result
print("The list after binary grouping : " + str(res))
```

**Output :**

```py
The original list : [(1, 56, 'M'), (1, 14, 'F'), (2, 43, 'F'), (2, 10, 'M')]
The list after binary grouping : [(1, 56, 14), (2, 43, 10)]

```