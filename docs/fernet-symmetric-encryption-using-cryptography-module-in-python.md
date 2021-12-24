# Python 中使用密码学模块的 Fernet(对称加密)

> 原文:[https://www . geesforgeks . org/fernet-对称-加密-使用-密码学-python 中的模块/](https://www.geeksforgeeks.org/fernet-symmetric-encryption-using-cryptography-module-in-python/)

密码学是在从一台计算机传输到另一台计算机或在计算机上存储数据时保护有用信息的实践。密码学处理明文加密成密文和密文解密成明文的问题。Python 支持一个加密包，可以帮助我们加密和解密数据。加密包的 fernet 模块具有生成密钥、将明文加密成密文以及分别使用加密和解密方法将密文解密成明文的内置功能。fernet 模块保证使用它加密的数据在没有密钥的情况下不能被进一步操作或读取。

**使用的方法:**

*   **generate_key() :** 这个方法生成一个新的 fernet key。密钥必须保持安全，因为它是解密密文的最重要的组成部分。如果密钥丢失，则用户无法再解密消息。此外，如果入侵者或黑客获得了密钥，他们不仅可以读取数据，还可以伪造数据。
*   **加密(数据):**它加密作为参数传递给方法的数据。这种加密的结果被称为“Fernet 令牌”，基本上就是密文。加密令牌还包含以明文生成时的当前时间戳。如果数据不是以字节为单位，encrypt 方法将引发异常。

> **参数:**
> 
> *   **数据**(字节)–要加密的明文。
> 
> **返回值:**没有密钥无法读取或更改的密文。它是 URL 安全的 base64 编码，被称为 Fernet 令牌。

*   **解密(令牌，ttl =无):**此方法解密作为参数传递给该方法的 Fernet 令牌。成功解密后，将获得原始明文，否则将引发异常。

> **参数:**
> 
> *   **令牌**(字节)–传递 Fernet 令牌(密文)进行解密。
> *   **TTL**(int)–可选地，可以在解密方法中提供一个整数作为第二个参数。ttl 表示令牌有效的时间。如果令牌早于 ttl 秒(从最初创建它的时间算起)，则会引发异常。如果 ttl 未作为参数传递，则不考虑令牌的年龄。如果令牌以某种方式无效，则会引发异常。
> 
> **返回值:**返回原始明文。

**编写程序的步骤:**

首先，需要使用以下命令安装加密软件包:

```py
pip install cryptography

```

## 蟒蛇 3

```py
# Fernet module is imported from the 
# cryptography package
from cryptography.fernet import Fernet

# key is generated
key = Fernet.generate_key()

# value of key is assigned to a variable
f = Fernet(key)

# the plaintext is converted to ciphertext
token = f.encrypt(b"welcome to geeksforgeeks")

# display the ciphertext
print(token)

# decrypting the ciphertext
d = f.decrypt(token)

# display the plaintext
print(d)
```

**输出:**

> b ' gaaaaabymsl 3 cjz8i 8sg 7 nwtdttottaqhtndgx4w 1 GW-9 yvrmbufz 3 bawnwvk 2 wjcrhjfayx7z 6 m1 idbchxpvd 2 dkpjypv9hlq 1 larwdf-re = '
> b '欢迎来到 geeksforgeeks '

解密的输出在原始消息前面有一个“b”，表示字节格式。但是，在打印原始邮件时，可以使用 decode()方法删除此内容。下面的程序实现了 decode()方法。

## 蟒蛇 3

```py
# Fernet module is imported from the 
# cryptography package
from cryptography.fernet import Fernet

# key is generated
key = Fernet.generate_key()

# value of key is assigned to a variable
f = Fernet(key)

# the plaintext is converted to ciphertext
token = f.encrypt(b"welcome to geeksforgeeks")

# display the ciphertext
print(token)

# decrypting the ciphertext
d = f.decrypt(token)

# display the plaintext and the decode() method 
# converts it from byte to string
print(d.decode())
```

**输出:**

> b ' gaaaaabymbeyetsu 6 bcyxr 9 aruibpeltu 5 axutwrfic 4 zzv 3 actmowdnsd 1 RH _ zrl 4 qz 7 TDI 1k 067 klx 0ma 3s 828 nstjlp 9 和 7l 0 _ zvycelzlaygk 3k = '
> 欢迎来到 geeksforgeeks