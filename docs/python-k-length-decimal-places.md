# Python–K 长度小数位

> 原文:[https://www . geesforgeks . org/python-k-length-小数位数/](https://www.geeksforgeeks.org/python-k-length-decimal-places/)

给定一个十进制数，将其位数扩展到 K 长度。

> **输入** : num = 76.8，K = 5
> **输出** : 76.80000
> **说明**:小数位长度为 5。
> 
> **输入** : num = 76.8，K = 6
> **输出** : 76.800000
> **说明**:小数位长度为 6。

**方法:使用格式()**

这是完成这项任务的方法。在本文中，我们利用多种格式兼容性来执行获取适当长度的小数位的任务。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# K length decimal Places
# Using format()

# initializing number 
num = 76.8

# printing original number 
print("The original number is : " + str(num))

# initializing K 
K = 7

# using format to solve this problem
res = "{{:.{}f}}".format(K).format(num)

# printing result 
print("The resultant number : " + str(res))
```

**Output**

```
The original number is : 76.8
The resultant number : 76.8000000

```