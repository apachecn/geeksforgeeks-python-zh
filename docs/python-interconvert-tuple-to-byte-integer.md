# Python–元组到字节整数的相互转换

> 原文:[https://www . geesforgeks . org/python-interconvert-tuple-to-byte-integer/](https://www.geeksforgeeks.org/python-interconvert-tuple-to-byte-integer/)

有时，在处理 Python 数据时，我们会遇到一个问题，即我们需要将元组值转换为组合字节，然后转换为整数，反之亦然。这种问题可以在数据领域得到应用。让我们讨论执行这项任务的某些方法。

> **输入** : test_tuple = (1，2，3，4，5)
> 输出 : 4328719365
> 
> **输入** : test_int = 4328719365
> **输出** : (1，2，3，4，5)

**方法#1 : Tuple - >字节整数:使用`int.from_bytes()`**
以上函数的组合可以用来解决这个问题。在本例中，我们使用内部函数 from_bytes()执行转换任务，并获得所需的整数值。

```py
# Python3 code to demonstrate working of 
# Interconvert Tuple to Byte Integer
# Tuple -> Byte Integer : Using int.from_bytes()

# initializing tuples
test_tuple = (6, 8, 3, 2)

# printing original tuple
print("The original tuple : " + str(test_tuple))

# Interconvert Tuple to Byte Integer
# Tuple -> Byte Integer : Using int.from_bytes()
res = int.from_bytes(test_tuple, byteorder ='big')

# printing result 
print("Tuple after conversion : " + str(res))
```

**Output :**

```py
The original tuple : (6, 8, 3, 2)
Tuple after conversion : 101188354

```

**方法#2:字节整数- >元组:使用`tuple.to_bytes()`**
以上函数的组合可以用来解决这个问题。在本例中，我们使用内部方法 to_bytes()执行转换任务，以获得所需的结果。

```py
# Python3 code to demonstrate working of 
# Interconvert Tuple to Byte Integer
# Using Byte Integer -> Tuple : Using tuple.to_bytes()

# initializing integer
test_int = 101188354

# printing original integer
print("The original integer : " + str(test_int))

# Interconvert Tuple to Byte Integer
# Using Byte Integer -> Tuple : Using tuple.to_bytes()
res = tuple(test_int.to_bytes(4, byteorder ='big'))

# printing result 
print("Integer after conversion : " + str(res))
```

**Output :**

```py
The original integer : 101188354
Integer after conversion : (6, 8, 3, 2)

```