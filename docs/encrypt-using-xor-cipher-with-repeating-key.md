# 使用重复密钥异或加密

> 原文:[https://www . geesforgeks . org/encrypt-use-xor-cipher-with-repeating-key/](https://www.geeksforgeeks.org/encrypt-using-xor-cipher-with-repeating-key/)

计算机体系结构有预定义的 ASCII 值&所有可打印字符的二进制形式，这允许我们像异或和大多数加密/解密算法依赖的那样按位操作逻辑。对明文进行异或运算，产生加密文本。

仅使用此技术加密纯文本所需的参数:

1.  Plain text (text that must be encrypted).
2.  Key (the unique byte of encrypted text, which can be of any length).

**加密处理:**

*   查找“纯文本”和“密钥”的长度。
*   将纯文本拆分成长度等于密钥长度的片段。
*   分别以各自的顺序用密钥对纯文本进行异或运算。
*   将上述异或运算结果存储在数组中。
*   循环完成后，数组包含整个加密文本。

**注意:**有时您可能需要填充纯文本，以防它没有很好地与一般的块大小对齐。下面是如何做到的

下面是加密*重复密钥异或*的代码；

## 蟒 3

```py
def repeated_key_xor(plain_text, key):

    # returns plain text by repeatedly xoring it with key
    pt = plain_text
    len_key = len(key)
    encoded = []

    for i in range(0, len(pt)):
        encoded.append(pt[i] ^ key[i % len_key])
    return bytes(encoded)

# Driver Code
def main():
    plain_text = b'Burning \'em, if you ain\'t quick and nimble\nI go crazy when I hear a cymbal'
    key = b'ICE'

    print("Plain text: ", plain_text)
    print("Encrypted as: ", repeated_key_xor(plain_text, key).hex())

if __name__ == '__main__':
    main()
```

**输出:**

> 纯文本:b“燃烧他们，如果你不快速和敏捷\nI 当我听到铙钹时会发疯”
> 
> 加密为:0b 3637272 a2 B2 e 63622 C2 e 69692 a 23693 a 2 3c 6324202d 623d 6343 c 2 a 2622632424272765272 a 282 B2 f 20430 a 652 e2c 652 a 3324202d 623d 6343 c 2626226326326324242