# hmac–用于消息认证的密钥散列

> 原文:[https://www . geesforgeks . org/hmac-key-hashing-message-authentication/](https://www.geeksforgeeks.org/hmac-keyed-hashing-message-authentication/)

HMAC 是一种使用加密散列函数的消息认证机制。HMAC 可以与任何迭代加密散列函数一起使用，例如 MD5，SHA-1，结合秘密共享密钥。
该模块实现了 HMAC 算法。基本思想是结合共享密钥生成实际数据的加密散列。产生的散列随后可用于检查传输或存储的消息，以确定信任级别，而无需传输密钥。

```py
 hmac.new(key, msg=None, digestmod=None) 
```

返回新的 hmac 对象。**密钥**是给出密钥的字节或字节数组对象。如果**消息**存在，则进行方法调用更新(msg)。 **digestmod** 是 HMAC 对象要使用的摘要名称、摘要构造函数或模块。它支持任何适合 hashlib.new()的名称。

HMAC 对象有以下方法:

1.  **HMAC.update(msg):** 这个方法用 msg 更新 HMAC 对象。重复调用相当于所有参数串联在一起的一次调用:m . update(a)；m.update(b)相当于 m.update(a + b)。
2.  **HMAC.digest():** 这个方法返回到目前为止传递给 update()方法的字节的摘要。这个 bytes 对象的长度将与给构造函数的摘要的 digest_size 相同。
3.  **HMAC.hexdigest():** 此方法类似于 digest()方法，不同的是，digest 作为长度两倍的字符串返回，仅包含十六进制数字。
4.  **HMAC.copy():** 此方法返回 HMAC 对象的副本或克隆。这可以用来有效地计算共享公共初始子串的字符串摘要。

哈希对象具有以下属性:

*   **HMAC.digest_size:** 结果 HMAC 摘要的大小，以字节为单位。
*   **HMAC.block_size:** 哈希算法的内部块大小，以字节为单位。
*   **HMAC.name:** 这个 HMAC 的规范名称。例如 hmac-sha1。

**示例:**

```py
# Python 3 code to demonstrate the working of hmac module.

import hmac
import hashlib

# creating new hmac object using sha1 hash algorithm
digest_maker = hmac.new(b'secret-key', b'msg', hashlib.sha1)

# print the Hexdigest of the bytes passed to update
print ("Hexdigest: " + digest_maker.hexdigest())

# call update to update msg
digest_maker.update(b'another msg')

# print the Hexdigest of the bytes passed to update
print ("Hexdigest after update: " + digest_maker.hexdigest())

print ("Digest size: " + str(digest_maker.digest_size) + " bytes")
print ("Block size: " + str(digest_maker.block_size) + " bytes")
print ("Canonical name: " + digest_maker.name)

# print the digest of the bytes passed to update
print ("Digest: ", end =" ")
print (digest_maker.digest())

# create a copy of the hmac object
digest_clone = digest_maker.copy()
print ("Hexdigest of clone: " + digest_clone.hexdigest())
```

**输出:**

```py
Hexdigest: df2ae7cdb5c849001e33ee29eb1c51ba2cafbaa7
Hexdigest after update: 3923273eb3aa9328478eb5aabf2d96e185256b4b
Digest size: 20 bytes
Block size: 64 bytes
Canonical name: hmac-sha1
Digest:  b"9#'>\xb3\xaa\x93(G\x8e\xb5\xaa\xbf-\x96\xe1\x85%kK"
Hexdigest of clone: 3923273eb3aa9328478eb5aabf2d96e185256b4b

```

本文由 **Mayank Agrawal** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。