# Python–从电子邮件地址中提取域名

> 原文:[https://www . geesforgeks . org/python-extract-domain-name-from-email-address/](https://www.geeksforgeeks.org/python-extract-domain-name-from-email-address/)

给定一个字符串电子邮件地址，提取域名。

> **输入**:test _ str = ' manjeet @ geeks . com '
> **输出**:geeks.com
> **说明**:域名，geeks.com 提取。
> 
> **输入**:test _ str = ' manjeet @ gfg . com '
> **输出**:gfg.com
> **说明**:域名，gfg.com 提取。

**方法#1:使用索引()+切片**

在本文中，我们利用了“@”符号是域名和电子邮件地址的本地部分的分隔符这一事实，因此，index()用于获取其索引，然后被切片直到结束。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Extract domain name from Email address
# Using index() + slicing 

# initializing strings
test_str = 'manjeet@geeksforgeeks.com'

# printing original string
print("The original string is : " + str(test_str))

# slicing domain name using slicing 
res = test_str[test_str.index('@') + 1 : ]

# printing result 
print("The extracted domain name : " + str(res)) 
```

**Output**

```py
The original string is : manjeet@geeksforgeeks.com
The extracted domain name : geeksforgeeks.com

```

**方法 2:使用 split()**

在本例中，我们在“@”上拆分字符串，并使用其第一个索引来获取所需的域名。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Extract domain name from Email address
# Using split()

# initializing strings
test_str = 'manjeet@geeksforgeeks.com'

# printing original string
print("The original string is : " + str(test_str))

# using split() to get domain name
res = test_str.split('@')[1]

# printing result 
print("The extracted domain name : " + str(res)) 
```

**Output**

```py
The original string is : manjeet@geeksforgeeks.com
The extracted domain name : geeksforgeeks.com

```