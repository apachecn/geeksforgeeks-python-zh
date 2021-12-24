# Python–将替代字符串转换为整数

> 原文:[https://www . geesforgeks . org/python-convert-alternate-string-character-to-integer/](https://www.geeksforgeeks.org/python-convert-alternate-string-character-to-integer/)

python 库很容易促进数据类型之间的相互转换。但是将字符串的替换列表转换成整数的问题在开发领域非常普遍。让我们讨论几个解决这个特殊问题的方法。

**方法#1:天真的方法**
这是任何程序员在执行这种操作时都会想到的最通用的方法。只需循环整个列表，并通过类型转换将列表字符串的替换转换为 int。

```
# Python 3 code to demonstrate 
# Alternate String to Integer Conversion
# using naive method 

# initializing list 
test_list = ['1', '4', '3', '6', '7']

# Printing original list
print ("Original list is : " + str(test_list))

# using naive method to
# perform conversion
for i in range(0, len(test_list)):
    if i % 2:
        test_list[i] = int(test_list[i])

# Printing modified list 
print ("Modified list is : " + str(test_list))
```

**Output :**

```
Original list is : ['1', '4', '3', '6', '7']
Modified list is : ['1', 4, '3', 6, '7']

```