# Python |交替前后求和

> 原文:[https://www . geesforgeks . org/python-alternate-front-real-sum/](https://www.geeksforgeeks.org/python-alternate-front-rear-sum/)

在使用 python 时，我们通常会遇到许多我们需要在日常工作和开发中解决的问题。特别是在开发中，python 的小任务希望只在一行中执行。我们讨论一些计算列表的方法，该列表由列表中前后交替的元素组成。
**方法#1:使用循环**
这是可以解决这个问题的蛮力方法。在这种情况下，我们取两个指针并将它们的和存储在数组中，同时增加和减少它们的位置。

## 蟒蛇 3

```py
# Python3 code to demonstrate
# Alternate front - rear Sum
# using loop

# initializing list
test_list = [1, 4, 5, 3, 6, 7]

# printing original list
print ("The original list is : " + str(test_list))

# Alternate front - rear Sum
# using loop
res = []
j = len(test_list) - 1
for i in range(0, len(test_list) // 2):
    res.append(test_list[i] + test_list[j])
    j = j - 1

# printing result
print ("The alternate front - rear Sum list is : " + str(res))
```

**Output**

```py
The original list is : [1, 4, 5, 3, 6, 7]
The alternate front - rear Sum list is : [8, 10, 8]

```

**方法 2:使用列表理解**
可以使用幼稚的方法来执行，但是列表理解提供了一个一个线性的方法来执行这个任务。

## 蟒蛇 3

```py
# Python3 code to demonstrate
# Alternate front - rear Sum
# using list comprehension

# initializing list
test_list = [1, 4, 5, 3, 6, 7]

# printing original list
print ("The original list is : " + str(test_list))

# Alternate front - rear Sum
# using list comprehension
res = [test_list[i] + test_list[len(test_list) - (i + 1)] for i in range(len(test_list) // 2)]

# printing result
print ("The alternate front - rear Sum list is : " + str(res))
```

**Output**

```py
The original list is : [1, 4, 5, 3, 6, 7]
The alternate front - rear Sum list is : [8, 10, 8]

```