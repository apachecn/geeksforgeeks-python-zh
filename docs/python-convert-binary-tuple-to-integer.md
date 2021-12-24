# Python–将二进制元组转换为整数

> 原文:[https://www . geesforgeks . org/python-convert-binary-tuple-to-integer/](https://www.geeksforgeeks.org/python-convert-binary-tuple-to-integer/)

给定二进制元组表示数字的二进制表示，将其转换为整数。

> **输入** : test_tup = (1，1，0)
> **输出** : 6
> **解释** : 4 + 2 = 6。
> 
> **输入** : test_tup = (1，1，1)
> 输出 : 7
> **解释** : 4 + 2 + 1 = 7。

**方法一:使用 join() +列表理解+ int()**

在本文中，我们使用 join()和 str()连接字符串格式的二进制元组，然后通过将 base 设为 2 来转换为整数。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Convert Binary tuple to Integer
# Using join() + list comprehension + int()

# initializing tuple
test_tup = (1, 1, 0, 1, 0, 0, 1)

# printing original tuple
print("The original tuple is : " + str(test_tup))

# using int() with base to get actual number
res = int("".join(str(ele) for ele in test_tup), 2) 

# printing result 
print("Decimal number is : " + str(res)) 
```

**Output**

```
The original tuple is : (1, 1, 0, 1, 0, 0, 1)
Decimal number is : 105

```

**方法 2:使用移位和|运算符**

在这种情况下，我们执行左移位，并使用 or 运算符获得二进制加法，从而计算结果。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Convert Binary tuple to Integer
# Using bit shift and | operator

# initializing tuple
test_tup = (1, 1, 0, 1, 0, 0, 1)

# printing original tuple
print("The original tuple is : " + str(test_tup))

res = 0
for ele in test_tup: 

    # left bit shift and or operator 
    # for intermediate addition
    res = (res << 1) | ele 

# printing result 
print("Decimal number is : " + str(res)) 
```

**Output**

```
The original tuple is : (1, 1, 0, 1, 0, 0, 1)
Decimal number is : 105

```