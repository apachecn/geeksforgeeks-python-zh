# Python | K 以上元素求和

> 原文:[https://www . geesforgeks . org/python-over-k-elements-summary/](https://www.geeksforgeeks.org/python-above-k-elements-summation/)

很多时候，我们可能会遇到这样的问题:我们需要求和而不是实际的数字，而且更多的时候，结果是有条件的..让我们讨论一下成功解决这个问题的某些方法。

**方法#1:使用循环**
这个问题可以很容易地通过使用带有强力方法的循环来解决，在这种方法中，我们可以在迭代时检查总和，并在前进时将其附加到新列表中。

```
# Python3 code to demonstrate
# Above K elements summation
# using loop

# initializing list 
test_list = [12, 10, 18, 15, 8, 18]

# printing original list
print("The original list : " + str(test_list))

# using loop
# Above K elements summation
res = 0
for idx in range(0, len(test_list)) :
    if test_list[idx] > 10:
        res += test_list[idx]

# print result
print("The summation of elements greater than 10 : " + str(res))
```

**Output :**

```
The original list : [12, 10, 18, 15, 8, 18]
The summation of elements greater than 10 : 63

```