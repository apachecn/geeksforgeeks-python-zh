# Python–获取随机范围平均值

> 原文:[https://www . geesforgeks . org/python-get-random-range-average/](https://www.geeksforgeeks.org/python-get-random-range-average/)

给定元素的范围和大小，提取一个范围内的随机数，并对其进行平均。

> **输入** : N = 3，strt_num = 10，end_num = 15
> **输出** : 13.58
> **解释**:10 到 15 之间抽取的随机元素，平均出 13.58。
> 
> **输入** : N = 2，strt_num = 13，end_num = 18
> **输出** : 15.82
> **说明**:本例中 2 个元素平均为 15.82。

**方法#1:使用 loop + `uniform()`**
以上功能的组合可以用来解决这个问题。在本文中，我们使用 uniform()执行提取数字的任务，循环用于执行数字相加。平均值在最后通过除以大小来计算。

```py
# Python3 code to demonstrate working of 
# Random Range Average
# Using loop + uniform()
import random

# initializing N
num = 4

# Initialize strt_num
strt_num = 15

# Initialize end_num
end_num = 60

# Using loop + uniform()
res = 0.0
for _ in range(num):     

    # performing summation of range elements
    res += random.uniform(strt_num, end_num)

# performing average
res = res / num

# printing result 
print("The average value : " + str(res)) 
```

**Output :**

```py
The average value : 42.980287235196116

```

**方法 2:使用`sum() + uniform()` +生成器表达式**
以上功能的组合可以解决这个问题。在本文中，我们使用 sum()来计算 sum()来执行求平均值的任务，并且使用生成器表达式将整个逻辑封装在一行中。

```py
# Python3 code to demonstrate working of 
# Random Range Average
# Using sum() + uniform() + generator expression
import random

# initializing N
num = 4

# Initialize strt_num
strt_num = 15

# Initialize end_num
end_num = 60

# Using sum() + uniform() + generator expression
# shorthand, using generator expression to form sum and division by Size
res = sum(random.uniform(strt_num, end_num) for _ in range(num)) / num

# printing result 
print("The average value : " + str(res))
```

**Output :**

```py
The average value : 42.980287235196116

```