# Python–给定字符串中第 Kth 索引处的访问元素

> 原文:[https://www . geesforgeks . org/python-access-element-at-kth-index-in-given-string/](https://www.geeksforgeeks.org/python-access-element-at-kth-index-in-given-string/)

给定一个字符串，访问 Kth 索引处的元素。

> **输入** : test_str = 'geeksforgeeks '，K = 4
> **输出** : s
> **说明** : s 为第 4 元素
> 
> **输入** : test_str = 'geeksforgeeks '，K = 24
> **输出**:字符串索引超出范围
> **解释**:异常为 K >字符串长度。

**方法#1:使用[]运算符**

这是执行这项任务的基本方式。在这种情况下，我们只需将 Kth 索引括在方括号中。如果 K 可以大于字符串长度，建议用 try-except 块括起来。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Access element at Kth index in String
# Using [] 

# initializing string
test_str = 'geeksforgeeks'

# printing original string
print("The original string is : " + str(test_str))

# initializing K
K = 7

# try-except block for error handling
try :

    # access Kth element
    res = test_str[K]
except Exception as e :
    res = str(e)

# printing result 
print("Kth index element : " + str(res)) 
```

**Output**

```
The original string is : geeksforgeeks
Kth index element : r

```

**方法 2:使用负指数+ len() + []运算符**

这是执行这项任务的另一种方式。在这种情况下，我们计算字符串的长度，并从中减去 K，得到从开始的第 K 个索引，以及负索引。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Access element at Kth index in String
# Using Negative index + len() + [] operator

# initializing string
test_str = 'geeksforgeeks'

# printing original string
print("The original string is : " + str(test_str))

# initializing K
K = 7

# try-except block for error handling
try :

    # access Kth element
    # using negative index
    res = test_str[-(len(test_str) - K)]
except Exception as e :
    res = str(e)

# printing result 
print("Kth index element : " + str(res)) 
```

**Output**

```
The original string is : geeksforgeeks
Kth index element : r

```