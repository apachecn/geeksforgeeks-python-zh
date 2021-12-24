# 使用 Python 中的 UUID 生成随机 id

> 原文:[https://www . geesforgeks . org/generating-random-ids-using-uuid-python/](https://www.geeksforgeeks.org/generating-random-ids-using-uuid-python/)

我们已经讨论了在 python 中生成唯一标识的方法，而不使用任何 Python 内置库[在 Python 中生成随机标识](https://www.geeksforgeeks.org/generating-random-ids-python/)

在本文中，我们将使用内置函数来生成它们。

UUID，通用唯一标识符，是一个 python 库，它帮助生成 128 位的随机对象作为 ID。它提供了唯一性，因为它根据时间、计算机硬件(MAC 等)生成 id。).

**UUID 优势:**

*   可以作为通用工具生成唯一的随机 id。
*   可用于加密和散列应用。
*   用于生成随机文档、地址等。

**方法 1:使用 uuid1()**

uuid1()在 uuid 库中定义，有助于使用 **MAC 地址和时间组件**生成随机 id。

```py
# Python3 code to generate the
# random id using uuid1()

import uuid

# Printing random id using uuid1()
print ("The random id using uuid1() is : ",end="")
print (uuid.uuid1())
```

输出:

```py
The random id using uuid1() is : 67460e74-02e3-11e8-b443-00163e990bdb

```

**uuid 1()**的表示

*   **字节:**以 16 字节字符串的形式返回 id。
*   **int :** 以 128 位整数的形式返回 id。
*   **十六进制:**以 32 个字符的十六进制字符串形式返回随机 id。

**uuid 1()的成分**

*   **版本:**UUID 版本号。
*   **变体:**决定 UUID 内部布局的变体。

**uuid 1()的字段**

*   **time _ low:**id 的前 32 位。
*   **time _ mid:**id 的下 16 位。
*   **time _ hi _ version:**id 的下 16 位。
*   **clock _ seq _ hi _ variant:**id 的下 8 位。
*   **clock _ seq _ low:**id 的下 8 位。
*   **节点:**id 的最后 48 位。
*   **时间:**id 的时间成分字段。
*   **clock_seq :** 14 位序列号。

```py
# Python3 code to demonstrate
# components, representations 
# and variants of uuid1()

import uuid

id = uuid.uuid1()

# Representations of uuid1()
print ("The Representations of uuid1() are : ")
print ("byte Representation : ",end="")
print (repr(id.bytes))

print ("int Representation : ",end="")
print (id.int)

print ("hex Representation : ",end="")
print (id.hex)

print("\n")

# Components of uuid1()
print ("The Components of uuid1() are : ")
print ("Version  : ",end="")
print (id.version)

print ("Variant : ",end="")
print (id.variant)

print("\n")

# Fields of uuid1()
print ("The Fields of uuid1() are : ")
print ("Fields  : ",end="")
print (id.fields)

print("\n")

# Time Component of uuid1()
print ("The time Component of uuid1() is : ")
print ("Time component  : ",end="")
print (id.node)
```

输出:

```py
The Representations of uuid1() are : 
byte Representation : b'k\x10\xa1n\x02\xe7\x11\xe8\xaeY\x00\x16>\x99\x0b\xdb'
int Representation : 142313746482664936587190810281013480411
hex Representation : 6b10a16e02e711e8ae5900163e990bdb

The Components of uuid1() are : 
Version  : 1
Variant : specified in RFC 4122

The Fields of uuid1() are : 
Fields  : (1796252014, 743, 4584, 174, 89, 95539497947)

The time Component of uuid1() is : 
Time component  : 95539497947

```

**缺点:**
这种方式包括使用计算机的 MAC 地址，因此会损害隐私，尽管它提供了唯一性。

**方法二:使用 uuid4()**
此功能保证随机号，不妥协隐私。

```py
# Python3 code to generate
# id using uuid4()

import uuid

id = uuid.uuid4()

# Id generated using uuid4()
print ("The id generated using uuid4() : ",end="")
print (id)
```

输出:

```py
The id generated using uuid4() : fbd204a7-318e-4dd3-86e0-e6d524fc3f98

```