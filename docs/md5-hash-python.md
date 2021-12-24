# Python 中的 MD5 哈希

> 原文:[https://www.geeksforgeeks.org/md5-hash-python/](https://www.geeksforgeeks.org/md5-hash-python/)

加密哈希在日常生活中使用，如数字签名、消息认证码、操作检测、指纹、校验和(消息完整性检查)、哈希表、密码存储等等。它们还用于通过网络发送消息以确保安全或将消息存储在数据库中。

python 中的“ **hashlib** 库中定义了很多哈希函数。
本文介绍 MD5 哈希的解释和工作原理。

**MD5 Hash**

该散列函数接受字节序列并返回 **128 位散列值**，通常用于检查数据完整性，但存在安全问题。

**相关功能:**

*   **encode() :** 将字符串转换为哈希函数可以接受的字节。
*   **digest() :** 返回字节格式的编码数据。
*   **hexdigest() :** 返回十六进制格式的编码数据。

下面的代码演示了 MD5 哈希接受字节并作为字节输出的工作方式。

```py
# Python 3 code to demonstrate the 
# working of MD5 (byte - byte)

import hashlib

# encoding GeeksforGeeks using md5 hash
# function 
result = hashlib.md5(b'GeeksforGeeks')

# printing the equivalent byte value.
print("The byte equivalent of hash is : ", end ="")
print(result.digest())
```

输出:

```py
The byte equivalent of hash is : b'\xf1\xe0ix~\xcetS\x1d\x11%Y\x94\\hq'

```

**说明:**以上代码取字节，可以被哈希函数接受。md5 哈希函数对其进行编码，然后使用 digest()，打印等效字节的编码字符串。

下面的代码演示了如何将字符串作为输入并输出十六进制等价的编码值。

```py
# Python 3 code to demonstrate the 
# working of MD5 (string - hexadecimal)

import hashlib

# initializing string
str2hash = "GeeksforGeeks"

# encoding GeeksforGeeks using encode()
# then sending to md5()
result = hashlib.md5(str2hash.encode())

# printing the equivalent hexadecimal value.
print("The hexadecimal equivalent of hash is : ", end ="")
print(result.hexdigest())
```

输出:

```py
The hexadecimal equivalent of hash is : f1e069787ece74531d112559945c6871

```

**说明:**上面的代码取 string，使用 encode()将其转换为等效字节，以便哈希函数可以接受。md5 哈希函数对其进行编码，然后使用 hexdigest()，打印十六进制等效编码字符串。