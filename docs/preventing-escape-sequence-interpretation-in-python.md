# 防止 Python 中的转义序列解释

> 原文:[https://www . geesforgeks . org/preventing-escape-sequence-解释-in-python/](https://www.geeksforgeeks.org/preventing-escape-sequence-interpretation-in-python/)

转义序列是具有非文字字符解释的字符组合(通常以转义字符为前缀)。使得被认为是转义序列的字符序列具有不同于其中包含的字面字符的含义。大多数编程语言使用*反斜杠\* 作为转义字符。该字符用作转义序列的起始字符，其后的任何字符(一个或多个)都被解释为转义序列。如果转义序列被指定为不可打印字符或控制代码，则该序列被称为控制字符。

**Python 中的转义序列列表:**

<figure class="table">

| **转义字符** | **表示** |
| --- | --- |
| \' | 单引号 |
| \" | 双引号 |
| \\ | 反斜线符号 |
| \n | 换行 |
| \r | 回车 |
| \t | 横表 |
| \b | 退格 |
| \f | 换页 |
| \v | 垂直标签 |
| \0 | 空字符 |
| \N{name} | 名为查找的 Unicode 字符数据库 |
| \ uxxxxxxxx x | 16 位十六进制值 XXXX 的 Unicode 字符 |
| \ Uxxxxxxxx | 32 位十六进制值为 XXXXXXXX 的 Unicode 字符 |
| \ooo | 八进制值 OOO 字符 |
| \xhh | 十六进制值为 HH 的字符 |

</figure>

上表适用于 Python 编程语言，因为不同的语言有不同的控制序列和控制字符，所以上表可能不适用于您选择的编程语言。《出埃及记》Windows 命令行解释器使用插入符号(**)来转义字符，因此上面的表在那里不适用。**

****转义序列解释****

**当字符串中遇到反斜杠时，转义序列解释完成。在遇到反斜杠(在一个字符串中)之后，任何后面的字符(带有( **\** ))将会出现在前面提到的表中。如果找到匹配，则从字符串中省略该序列，并使用与该序列相关联的翻译。如果没有找到匹配项，则不会发生查找，并且控制序列按原样复制。**

****例****

## **蟒蛇 3**

```
# A string with a recognized escape sequence
print("I will go\tHome")

# A string with a unrecognized escape sequence
print("See you\jtommorow")
```

****输出:****

```
I will go    Home
See you\jtommorow
```

**如上面的输出所示，第一个 print 语句产生了一个输出，其中 **\t** 被解析为一个垂直标签，并在输出中被省略。另一方面，在第二个打印声明中， **\j** 仍然存在，因为不存在该序列的法律解决方案。**

## ****防止逃逸序列解释****

**有些情况下，我们不希望字符串以这种方式运行。在这些情况下，我们通常希望保留反斜杠。可能需要这样做的一些情况是:**

*   **字符串包含网络或本地路径**
*   **字符串包含正则表达式，正则表达式引擎将进一步处理该字符串**

### ****预防方法****

****方法 1:****

**不断加倍反斜杠，也让我们能够克服这样的问题。在这个方法中，我们手动查找字符串中的每一个反斜杠，并将另一个反斜杠连接到它(在它的直接位置)。一般来说，这是一个繁琐的方法，只有在字符串较小的情况下才建议使用。**

## **蟒蛇 3**

```
# sample string
s = "I love to use \t instead of using 4 spaces"

# normal output
print(s)

# doubling line backslashes
s = "I love to use \\t instead of using 4 spaces"

# output after doubling
print(s)
```

****输出:****

```
I love to use      instead of using 4 spaces
I love to use \t instead of using 4 spaces
```

****方法二:****

**使用 **r'…'**或**R '……'**构建。通常称为原始字符串，用于将转义序列保留为文本。这样它就可以像以前的方法一样自动完成(不需要人工干预)。要将正常字符串转换为原始字符串，请在字符串前加上一个 **r** 或**r**前缀。这是克服转义序列问题的选择方法。**

## **蟒蛇 3**

```
s = "C:\Program Files\norton\appx"

# normal output
print(s)

# changing the string into a raw string
s = r"C:\Program Files\norton\appx"

# Outputting the raw versio of the string
print(s)
```

****输出:****

```
C:\Program Files
ortonppx
C:\Program Files\norton\appx
```

**由于转义字符引起的问题不一定会导致不希望的输出，还会出现*错误。*例如，下面的代码在执行时会产生一个错误。**

## **蟒蛇 3**

```
print("C:\Users\Desktop\JSON")
```

**产生以下错误**

> **print(" c:\ users \ desktop \ JSON ")
> ^
> 语法错误:(unicode 错误)“unicodeescape”编解码器无法解码位置 2-3 中的字节:截断\ uxxxxxxxx 转义**

**导致该错误的原因是字符串中的 **\U** 导致接下来的 4 个字符被视为 32 位十六进制值，该值对应于一个 Unicode 代码点。这会导致一个错误，因为下一个角色是 ***s*** ，它们在 16 基数范围之外。**