# 在 Python 中生成随机数列表

> 原文:[https://www . geesforgeks . org/generating-随机数列表-in-python/](https://www.geeksforgeeks.org/generating-random-number-list-in-python/)

有时，在制作游戏或赌博程序时，我们会遇到用随机数创建列表的任务。这个任务通常是使用循环和一个接一个地附加随机数来执行的。但是总是要求以最简洁的方式执行此操作。让我们讨论一下实现这一点的某些方法。

### **方法#1:使用列表理解+ randrange()**

使用列表理解可以缩短执行这个特殊任务的简单方法。randrange 函数用于执行生成随机数的任务。

## 蟒蛇 3

```
# Python3 code to demonstrate
# to generate random number list
# using list comprehension + randrange()
import random

# using list comprehension + randrange()
# to generate random number list
res = [random.randrange(1, 50, 1) for i in range(7)]

# printing result
print ("Random number list is : " +  str(res))
```

**Output**

```
Random number list is : [30, 48, 14, 33, 1, 4, 18]

```