# 初始化 Python 中的空字典

> 原文:[https://www . geesforgeks . org/initialize-一个空的 python 字典/](https://www.geeksforgeeks.org/initialize-an-empty-dictionary-in-python/)

[**Python 中的字典**](https://www.geeksforgeeks.org/python-dictionary/) 是一个无序的数据值集合，用于像地图一样存储数据值，与其他只保存单个值作为元素的数据类型不同，字典保存**键:值**对。字典中提供了键值，以使其更加优化。

现在，让我们看看创建空字典的不同方法。

**方法 1:** 使用 **{ }** 符号。

我们可以通过在赋值语句中不给出花括号中的元素来创建一个空字典对象

**代码:**

## 蟒蛇 3

```
# Python3 code to demonstrate use of
# {} symbol to initialize dictionary
emptyDict = {}

# print dictionary
print(emptyDict)

# print length of dictionary
print("Length:", len(emptyDict))

# print type
print(type(emptyDict))
```

**Output**

```
{}
Length: 0
<class 'dict'>

```

**方法二:**使用 **dict()** 内置功能。

空字典也是由 dict()内置函数创建的，没有任何参数。

**代码:**

## 蟒蛇 3

```
# Python3 code to demonstrate use of 
# dict() built-in function to
# initialize dictionary
emptyDict = dict()

# print dictionary
print(emptyDict)

# print length of dictionary
print("Length:",len(emptyDict))

# print type
print(type(emptyDict))
```

**Output**

```
{}
Length: 0
<class 'dict'>

```