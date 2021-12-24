# 使用 gnboorse-rom 模块将 Python 中的罗马转换为十进制

> 原文:[https://www . geeksforgeeks . org/转换-python 中的罗马到十进制-使用-gnboorse-rom-module/](https://www.geeksforgeeks.org/converting-roman-to-decimal-in-python-using-gnboorse-rom-module/)

一个 **gnboorse-rom** 模块是 python 库，帮助你把罗马数字转换成十进制数字，十进制数字转换成罗马数字。它可以转换罗马数字和十进制中高达 3999 的值。

**注:**以下是一些独特的罗马符号及其对应的十进制值的列表。

```
SYMBOL        VALUE
I      ->       1
IV     ->       4
V      ->       5
IX     ->       9
X      ->       10
XL     ->       40
L      ->       50
XC     ->       90
C      ->       100
CD     ->       400
D      ->       500
CM     ->       900 
M      ->       1000       

```

罗马数字中的数字是由这些符号按降序排列而成的字符串(例如，先写 M，后写 D，等等)。).然而，在一些特定的情况下，为了避免四个字符连续重复(如 IIII 或 XXXX)，减法符号经常被使用如下:

*   我放在 V 或 X 前面表示少了一个，所以四是 IV(少了一个 5)，九是 IX(少了一个 10)。
*   放在 L 或 C 前面的 x 表示少了十个，所以四十是 XL (10 比 50 少)，90 是 XC(十比一百少)。
*   放在 D 或 M 前面的 c 表示少了一百，所以四百是 CD(一百少于五百)，九百是 CM(一百少于一千)。

#### 安装库

这个模块没有内置 Python。你需要从外部安装它。要安装此模块，请在终端中键入以下命令。

```
pip install gnboorse-rom
```

**通用只读存储器的功能:**

*   **1-rom_generate :**: It will convert our decimal number into roman numeral and will return a roman numeral string as a output .
    **Example :**

    ```
    # Importing rom_generate function  
    # From gnboorse's rom Library  
    from rom import rom_generate

    a = rom_generate(1)
    print(a)

    a = rom_generate(5)
    print(a)

    a = rom_generate(15)
    print(a)

    a = rom_generate(255)
    print(a)

    a = rom_generate(512)
    print(a)

    a = rom_generate(786)
    print(a)

    a = rom_generate(1444)
    print(a)

    a = rom_generate(2000)
    print(a)

    a = rom_generate(3999)
    print(a)
    type(a)
    ```

    **输出:**

    ```
    I
    V
    XV
    CCLV
    DXII
    DCCLXXXVI
    MCDXLIV
    MM
    MMMCMXCIX
    str

    ```

*   **2-rom_parse**:It will convert our roman numeral into decimal number and will return a decimal integer number as a output .
    **Example :**

    ```
    # Importing rom_parse function  
    # From gnboorse's rom Library  
    from rom import rom_parse

    a = rom_parse('I')
    print(a)

    a = rom_parse('XV')
    print(a)

    a = rom_parse('L')
    print(a)

    a = rom_parse('CCLV')
    print(a)

    a = rom_parse('CD')
    print(a)

    a = rom_parse('MXII')
    print(a)

    a = rom_parse('DDD')
    print(a)

    a = rom_parse('MMD')
    print(a)

    a = rom_parse('MMMCMXCIX')
    print(a)
    type(a)
    ```

    **输出:**

    ```
    1
    15
    50
    255
    400
    1012
    1500
    2500
    3999
    int

    ```

**注:**要了解逻辑背后的代码，可以参考 [GeeksforGeeks](https://www.geeksforgeeks.org/converting-decimal-number-lying-between-1-to-3999-to-roman-numerals/)