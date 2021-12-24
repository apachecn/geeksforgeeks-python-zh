# Python |查找所有元组是否长度相同

> 原文:[https://www . geesforgeks . org/python-find-是否所有元组都具有相同长度/](https://www.geeksforgeeks.org/python-find-whether-all-tuple-have-same-length/)

给定一个元组列表，任务是找出是否所有元组都具有相同的长度。
下面是一些实现上述任务的方法。
**方法#1:使用迭代**

## 蟒蛇 3

```py
# Python code to find whether all
# tuple have equal length

# Input List initialization
Input = [(11, 22, 33), (44, 55, 66)]

# printing
print("Initial list of tuple", Input)

# K Initialization
k = 3
flag = 1

# Iteration
for tuple in Input:
    if len(tuple) != k:
        flag = 0
        break

# Checking whether all tuple
# have length equal to 'K' in list of tuple
if flag:
    print("All tuples have same length")
else:
    print("Tuples does not have same length")
```

**Output:** 

```py
Initial list of tuple [(11, 22, 33), (44, 55, 66)]
All tuples have same length
```

**方法 2:使用 all()**

## 蟒蛇 3

```py
# Python code to find whether all tuple
# have equal length

# Input list initialization
Input = [(11, 22, 33), (44, 55, 66), (11, 23)]
k = 2

# Printing
print("Initial list of tuple", Input)

# Using all()
Output =(all(len(elem) == k for elem in Input))

# Checking whether all tuple
# have equal length
if Output:
    print("All tuples have same length")
else:
    print("Tuples does not have same length")
```

**Output:** 

```py
Initial list of tuple [(11, 22, 33), (44, 55, 66), (11, 23)]
Tuples does not have same length
```