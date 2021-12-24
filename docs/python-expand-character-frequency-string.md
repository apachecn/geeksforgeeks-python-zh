# Python–扩展字符串频率

> 原文:[https://www . geesforgeks . org/python-expand-character-frequency-string/](https://www.geeksforgeeks.org/python-expand-character-frequency-string/)

给定一个字符串，哪个字符后跟它的频率，创建适当的字符串。

**示例:**

> **输入**:test _ str = ' g7f2g 3 i2s 2 B3 e 4 '
> 输出**:gggggggffggisisbbeee
> **解释** : g 接 7，重复 7 次。**
> 
>  ****输入** : test_str = 'g1f1g1'
> **输出** : gfg
> **解释** : f 成功 1，重复 1 次。**

****方法#1:使用**[**zip()**](https://www.geeksforgeeks.org/zip-in-python/)**+**[**join()**](https://www.geeksforgeeks.org/join-function-python/)**

**这是执行这项任务的方法之一。在这种情况下，使用 [join()](https://www.geeksforgeeks.org/join-function-python/) 完成连接适当字符的任务，并且使用 [zip()](https://www.geeksforgeeks.org/zip-in-python/) 来转换不同的频率和字符串。缺点是字符的频率被限制在 1 位数。**

## **蟒蛇 3**

```py
# Python3 code to demonstrate working of 
# Expand Character Frequency String 
# Using join() + zip()
import re

# initializing string
test_str = 'g7f2g3i2s2b3e4s5t6'

# printing original string
print("The original string is : " + str(test_str))

# using zip() to pair up numbers and characters 
# seperately
res = "".join(a *int(b) for a, b in zip(test_str[0::2], test_str[1::2]))

# printing result 
print("The expanded string : " + str(res)) 
```

****Output**

```py
The original string is : g7f2g3i2s2b3e4s5t6
The expanded string : gggggggffgggiissbbbeeeessssstttttt

```** 

****方法 2:使用 regex() + join()****

**这是执行这项任务的另一种方式。在这个任务中，将数字和字符配对到不同的字符串是使用正则表达式()执行的，优点是它可以接受数字超过 2 的数字。**

## **蟒蛇 3**

```py
# Python3 code to demonstrate working of 
# Expand Character Frequency String 
# Using regex() + join()
import re

# initializing string
test_str = 'g7f2g3i2s2b3e4s5t10'

# printing original string
print("The original string is : " + str(test_str))

# using findall to pair up numbers and characters 
# seperately, can include longer digit strings
res = ''.join(chr * int(num or 1) 
              for chr, num in re.findall(r'(\w)(\d+)?', test_str))

# printing result 
print("The expanded string : " + str(res)) 
```

****Output**

```py
The original string is : g7f2g3i2s2b3e4s5t10
The expanded string : gggggggffgggiissbbbeeeessssstttttttttt

```**