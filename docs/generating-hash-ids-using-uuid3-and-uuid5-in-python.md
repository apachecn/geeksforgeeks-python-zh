# 使用 Python 中的 uuid3()和 uuid5()生成哈希 id

> 原文:[https://www . geeksforgeeks . org/generating-hash-ids-using-uuid 3-和-uuid5-in-python/](https://www.geeksforgeeks.org/generating-hash-ids-using-uuid3-and-uuid5-in-python/)

Python 的 [UUID](https://www.geeksforgeeks.org/generating-random-ids-using-uuid-python/) 类定义了四个函数，每个函数生成不同版本的 UUID。让我们看看如何使用 **uuid3()** 和 **uuid5()** 基于 MD5 和 SHA-1 哈希生成 UUID。
加密哈希可以用来生成不同的标识，以名称空间标识符和字符串作为输入。支持加密哈希生成的函数有:

1.  **uuid3(名称空间，字符串):**该函数使用与字符串一起提及的名称空间的 **MD5** 哈希值来生成该特定字符串的随机 id。
2.  **uuid5(名称空间，字符串):**该函数使用与字符串一起提及的名称空间的 **SHA-1** 哈希值来生成该特定字符串的随机 id。

uuid 模块定义了以下用于 uuid3()或 uuid5()的命名空间标识符:

> **NAMESPACE_DNS** :当名称字符串为全限定域名时使用。
> **NAMESPACE_URL** :当名称字符串为 URL 时使用。
> **NAMESPACE_OID** :当名称字符串为 ISO OID 时使用。
> **NAMESPACE_X500** :当名称字符串为 DER 中的 X.500 DN 或文本输出格式时使用。

**代码#1 :**

## 蟒蛇 3

```
# Python3 code to demonstrate working
# of uuid3() and uuid5()
import uuid

# initializing a string
url = "https://www.geeksforgeeks.org/fibonacci-sum-subset-elements/"

# using NAMESPACE_URL as namespace
# to generate MD5 hash uuid
print ("The SHA1 hash value generated ID is : ",
            uuid.uuid3(uuid.NAMESPACE_URL, url))

# using NAMESPACE_URL as namespace 
# to generate SHA-1 hash uuid
print ("The MD5 hash value generated ID is : ",
            uuid.uuid5(uuid.NAMESPACE_URL, url))
```

**Output:** 

```
The SHA1 hash value generated ID is :  e13a319e-16d9-3ff5-a83c-96564007998e
The MD5 hash value generated ID is :  dbe3178d-4b83-5024-9b26-9b8e1b280514
```

**代码#2 :**

## 蟒蛇 3

```
# Python3 code to demonstrate working 
# of uuid3() and uuid5()
import uuid

# initializing a string
qualified_dns = "www.geeksforgeeks.org"

# using NAMESPACE_DNS as namespace
# to find MD5 hash id
print ("The SHA1 hash value generated ID is : ",
    uuid.uuid3(uuid.NAMESPACE_DNS, qualified_dns))

# using NAMESPACE_DNS as namespace
# to generate SHA-1 hash id
print ("The MD5 hash value generated ID is : ",
    uuid.uuid5(uuid.NAMESPACE_DNS, qualified_dns))
```

**Output:** 

```
The SHA1 hash value generated ID is :  adbed9f7-bbe3-376f-b88d-2018b8f6db07
The MD5 hash value generated ID is :  f72cdf8a-b361-50b2-9451-37a997f8675d
```

**注:**ID 生成为 2 步流程。首先，进行字符串和名称空间的连接，然后作为输入提供给相应的函数，以返回 128 UUID 生成的。如果再次选择具有相似字符串的相同 NAMESPACE 值，则生成的 ID 也将相同。

**参考:**https://docs.python.org/2/library/uuid.html