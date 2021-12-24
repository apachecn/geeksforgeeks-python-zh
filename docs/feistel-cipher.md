# 费斯特密码

> 原文:[https://www.geeksforgeeks.org/feistel-cipher/](https://www.geeksforgeeks.org/feistel-cipher/)

Feistel 密码模型是一种用于开发许多分组密码(如 DES)的结构或设计。Feistel 密码在其设计中可能有可逆、不可逆和自可逆的成分。使用相同的加密和解密算法。每轮使用一把单独的钥匙。然而，相同的轮密钥用于加密和解密。

## 费斯特密码算法

*   创建所有纯文本字符的列表。

*   将纯文本转换为 Ascii，然后转换为 8 位二进制格式。

*   将二进制纯文本字符串分成两半:左半部分(L1)和右半部分(R1)

*   为两轮生成长度等于纯文本长度一半的随机二进制密钥(K1 和 K2)。

第一轮加密

*   **a.** 使用 R1 和 K1 生成函数 f1，如下所示:

```py
f1= xor(R1, K1)
```

*   **b.** 现在第一轮之后新的左半区(L2)和右半区(R2)如下:

```py
R2= xor(f1, L1)
L2=R1
```

第二轮加密

*   **a.** 使用 R2 和 K2 生成函数 f2，如下所示:

```py
f2= xor(R2, K2)
```

*   **b.** 现在第一轮之后新的左半区(L2)和右半区(R2)如下:

```py
R3= xor(f2, L2)
L3=R2
```

*   R3 到 L3 的连接是密文
*   解密时使用相同的算法从密文中检索纯文本。

**示例:**

```py
Plain Text is: Hello
Cipher Text:  E1!w(
Retrieved Plain Text is:  b'Hello'

Plain Text is: Geeks
Cipher Text: O;Q
Retrieved Plain Text is:  b'Geeks'
```

## 蟒蛇 3

```py
# Python program to demonstrate
# Feistel Cipher Algorithm

import binascii

# Random bits key generation
def rand_key(p):

    import random
    key1 = ""
    p = int(p)

    for i in range(p):

        temp = random.randint(0,1)
        temp = str(temp)
        key1 = key1 + temp

    return(key1)

# Function to implement bit exor
def exor(a,b):

    temp = ""

    for i in range(n):

        if (a[i] == b[i]):
            temp += "0"

        else:
            temp += "1"

    return temp

# Defining BinarytoDecimal() function
def BinaryToDecimal(binary):

    # Using int function to convert to
    # string   
    string = int(binary, 2)

    return string

# Feistel Cipher
PT = "Hello"
print("Plain Text is:", PT)

# Converting the plain text to
# ASCII
PT_Ascii = [ord(x) for x in PT]

# Converting the ASCII to
# 8-bit binary format
PT_Bin = [format(y,'08b') for y in PT_Ascii]
PT_Bin = "".join(PT_Bin)

n = int(len(PT_Bin)//2)
L1 = PT_Bin[0:n]
R1 = PT_Bin[n::]
m = len(R1)

# Generate Key K1 for the
# first round
K1= rand_key(m)

# Generate Key K2 for the
# second round
K2= rand_key(m)

# first round of Feistel
f1 = exor(R1,K1)
R2 = exor(f1,L1)
L2 = R1

# Second round of Feistel
f2 = exor(R2,K2)
R3 = exor(f2,L2)
L3 = R2

# Cipher text
bin_data = L3 + R3
str_data =' '

for i in range(0, len(bin_data), 7):

    # slicing the bin_data from index range [0, 6]
    # and storing it in temp_data
    temp_data = bin_data[i:i + 7]

    # passing temp_data in BinarytoDecimal() function
    # to get decimal value of corresponding temp_data
    decimal_data = BinaryToDecimal(temp_data)

    # Decoding the decimal value returned by 
    # BinarytoDecimal() function, using chr() 
    # function which return the string corresponding 
    # character for given ASCII value, and store it 
    # in str_data
    str_data = str_data + chr(decimal_data)

print("Cipher Text:", str_data)

# Decryption
L4 = L3
R4 = R3

f3 = exor(L4,K2)
L5 = exor(R4,f3)
R5 = L4

f4 = exor(L5,K1)
L6 = exor(R5,f4)
R6 = L5
PT1 = L6+R6

PT1 = int(PT1, 2)
RPT = binascii.unhexlify( '%x'% PT1)
print("Retrieved Plain Text is: ", RPT)
```

**输出:**

```py
Plain Text is: Hello
Cipher Text:  E1!w(
Retrieved Plain Text is:  b'Hello'
```