# Python–编辑元组内的对象

> 原文:[https://www . geesforgeks . org/python-edit-objects-inside-tuple/](https://www.geeksforgeeks.org/python-edit-objects-inside-tuple/)

有时，在处理元组时，不可变会给元组的工作带来很多混乱。脑海中可能浮现的一个问题是，元组中的对象是可变的吗？。答案是**是**。让我们讨论一下实现这一点的某些方法。

**方法#1:使用访问方法**
这是可以执行元组内部对象编辑的方法之一。这类似于任何其他容器和使用列表访问方法的地方。

```py
# Python3 code to demonstrate working of 
# Edit objects inside tuple
# Using Access Methods

# initializing tuple
test_tuple = (1, [5, 6, 4], 9, 10)

# printing original tuple
print("The original tuple : " + str(test_tuple))

# Edit objects inside tuple
# Using Access Methods
test_tuple[1][2] = 14

# printing result 
print("The modified tuple : " + str(test_tuple)) 
```

**Output :**

```py
The original tuple : (1, [5, 6, 4], 9, 10)
The modified tuple : (1, [5, 6, 14], 9, 10)

```