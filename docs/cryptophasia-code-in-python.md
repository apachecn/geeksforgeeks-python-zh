# Python 中的隐孢子虫代码

> 原文:[https://www.geeksforgeeks.org/cryptophasia-code-in-python/](https://www.geeksforgeeks.org/cryptophasia-code-in-python/)

**隐语症**是一种在双胞胎学习自己的母语之前就在他们之间创造和使用的语言。既然没有人知道那种语言，它仍然是一个秘密。由于人类从未想尽一切办法，科学家们发现，这种语言是通过念错我们都知道的现有语言而创造出来的。这不提醒你加密吗？是的，很相似。我们所需要做的是，改变特定语言的一些语法规则，这样读者就应该知道这些规则，以便解密它们。

## 使用的技术

众所周知，如果拼错的单词的第一个和最后一个字母是正确的，我们仍然可以正确地读出来。因此，这就解释了单词的第一个和最后一个字母在正确阅读中的重要性。隐孢子虫明智地使用这种技术来加密一个单词。它改变单词的首字母和末字母，并对其进行加密。现在让我们看看为了达到这种状态而遵循的规则，这样除了知道这些规则的人，没有人能解密这些单词。

### 规则:

*   去掉单词的第一个字母。见下例

```py
apple --> pple
```

*   将第一个字母附加到单词的末尾。

```py
pple --> pplea
```

*   将字符串“ay”附加到单词的末尾。

```py
pplea --> ppleaay
```

“apple”这个词已经被加密成了“ppleaay”。这样，任何单词都可以加密成未知的形式，读者很难理解。

### 履行

在编码之前，我们应该知道输入可以是任何形式。它们可能包含大写和小写字母、特殊字符、空格和数字。为了有效地加密，我们不会使用大写字母和特殊字符。因为当这些大写和特殊字符出现在单词中时，它甚至可以为读者提供关于这个单词的线索。

几个 ***情况*** 可以如下:

*   大写字母大多出现在单词的开头。这可以给他们一个关于起始字母的线索。
*   一些特殊字符只在少数格式中使用，如电子邮件标识中的@和电话号码中的+等。

这让我们意识到我们真的需要:

*   将 ***大写*** 转换为小写字母。
*   移除 ***特殊字符*** 。

由于字符串是不可变的，所以很难对给定的单词进行更改。因此，将字符串转换成可变的列表是非常必要的。在我们的程序中，因为我们在玩一个单词的字母，所以把这个单词的字母拆分成一个列表是很重要的。

下面是实现。

## 蟒蛇 3

```py
# Cleaning & Converting Text into List
def CleConvStr2List(text):
    A, B, C = ([] for i in range(3))

    # Split line into words
    A = text.split()

    # Removing special chars from word
    for i in range(len(A)):
        B.append(''.join(e for e in A[i] if e.isalnum()))

    while('' in B):
        B.remove("")

    # Split word into chars
    for i in range(len(B)):
        C.append(list(B[i]))

    return C

# Performing Cryptophasia
def Cryptophasia(text):
    C = []
    C = CleConvStr2List(text)

    for i in range(len(C)):
        C[i].append(C[i][0])
        C[i].append('a')
        C[i].append('y')
        del C[i][0]

    D = []
    word = ''

    for i in range(len(C)):
        D.append(word.join(C[i]))

    return " ".join(D)

# Driver Code
print(Cryptophasia('Apple'))
print(Cryptophasia('GeeksforGeeks'))
print(Cryptophasia('happy'))
```

**输出:**

```py
ppleAay
eeksforGeeksGay
appyhay
```