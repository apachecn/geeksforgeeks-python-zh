# Python–查找范围内而非集合内的数字

> 原文:[https://www . geesforgeks . org/python-查找范围内和不在集合中的数字/](https://www.geeksforgeeks.org/python-find-numbers-in-range-and-not-in-set/)

给定一组数字和一个范围，任务是编写一个 Python 程序来提取范围内所有不在组内的数字。

**示例:**

```
Input : test_set = {6, 4, 2, 7, 9}, low, high = 5, 10
Output : [5, 8]
Explanation : 6, 7 and 9 are present in set, remaining 5, 8 are in output.

Input : test_set = {6, 4, 2, 7, 9}, low, high = 5, 8
Output : [5]
Explanation : 6 and 7 are present in set, remaining 5 is in output.
```

**方法#1:使用循环**

在这种情况下，我们迭代范围内的所有元素，并使用条件语句从结果中省略集合中不存在的元素。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Range Numbers not in set
# Using loop

# initializing set
test_set = {6, 4, 2, 7, 9}

# printing original set
print("The original set is : " + str(test_set))

# initializing range
low, high = 5, 10

res = []
for ele in range(low, high):

    # getting elements not in set
    if ele not in test_set:
        res.append(ele)

# printing result
print("Elements not in set : " + str(res))
```

**输出:**

```
The original set is : {2, 4, 6, 7, 9}
Elements not in set : [5, 8]
```

**方法 2:使用“-”运算符**

在本例中，我们使用“-”运算符执行通过集合元素从范围中获取差异的任务。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Range Numbers not in set
# Using "-" operator

# initializing set
test_set = {6, 4, 2, 7, 9}

# printing original set
print("The original set is : " + str(test_set))

# initializing range
low, high = 5, 10

# using "-" operator to get difference
res = list(set(range(low, high)) - test_set)

# printing result
print("Elements not in set : " + str(res))
```

**输出:**

```
The original set is : {2, 4, 6, 7, 9}
Elements not in set : [8, 5]
```