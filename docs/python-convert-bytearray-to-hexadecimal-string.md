# Python |将字节数组转换为十六进制字符串

> 原文:[https://www . geesforgeks . org/python-convert-bytearray-to-十六进制-string/](https://www.geeksforgeeks.org/python-convert-bytearray-to-hexadecimal-string/)

有时，我们可能会遇到需要处理异常数据类型转换的问题。一种这样的转换可以是将字节列表(字节数组)转换为十六进制字符串格式。让我们讨论一下实现这一点的某些方法。

**方法#1:使用`format() + join()`**
上述功能的组合可用于执行该特定任务。format 函数将字节转换为十六进制格式。格式中的“02”用于填充所需的前导零。join 函数允许将十六进制结果连接成字符串。

```py
# Python3 code to demonstrate working of
# Converting bytearray to hexadecimal string
# Using join() + format()

# initializing list 
test_list = [124, 67, 45, 11]

# printing original list 
print("The original string is : " + str(test_list))

# using join() + format()
# Converting bytearray to hexadecimal string
res = ''.join(format(x, '02x') for x in test_list)

# printing result 
print("The string after conversion : " + str(res))
```

**Output :**

```py
The original string is : [124, 67, 45, 11]
The string after conversion : 7c432d0b

```