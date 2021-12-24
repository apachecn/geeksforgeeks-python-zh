# 在 Python 中求列表的和与平均值

> 原文:[https://www . geesforgeks . org/find-sum-and-average-of-list-in-python/](https://www.geeksforgeeks.org/find-sum-and-average-of-list-in-python/)

给定一个列表。任务是找出列表的总和和平均值。列表的平均值定义为元素的总和除以元素的数量。

**示例:**

```py
Input: [4, 5, 1, 2, 9, 7, 10, 8]
Output:
sum =  46
average =  5.75

Input: [15, 9, 55, 41, 35, 20, 62, 49]
Output:
sum =  286
average =  35.75

```

**方法一:天真法**

在这个方法中，我们将遍历列表，并将每个元素添加到一个变量计数中，该计数存储第 i <sup>个</sup>元素的和，然后将该和除以变量的总数，得到平均值。

**示例:**

## 蟒蛇 3

```py
# Python program to find the sum
# and average of the list

L = [4, 5, 1, 2, 9, 7, 10, 8]

# variable to store the sum of 
# the list
count = 0

# Finding the sum
for i in L:
    count += i

# divide the total elements by
# number of elements
avg = count/len(L)

print("sum = ", count)
print("average = ", avg)
```

**输出:**

```py
sum =  46
average =  5.75

```

**方法二:使用 sum()方法**

[sum()](https://www.geeksforgeeks.org/sum-function-python/) 方法返回作为参数传递的列表的和。然后我们将总和除以 len()方法得到平均值。

**示例:**

## 蟒蛇 3

```py
# Python program to find the sum
# and average of the list

L = [4, 5, 1, 2, 9, 7, 10, 8]

# using sum() method
count = sum(L)

# finding average
avg = count/len(L)

print("sum = ", count)
print("average = ", avg)
```

**输出:**

```py
sum =  46
average =  5.75

```