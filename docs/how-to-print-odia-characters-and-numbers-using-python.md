# 如何使用 Python 打印 Odia 字符和数字？

> 原文:[https://www . geeksforgeeks . org/如何使用 python 打印字符和数字/](https://www.geeksforgeeks.org/how-to-print-odia-characters-and-numbers-using-python/)

[Odia(ଓଡ଼ିଆ语](https://en.wikipedia.org/wiki/Odia_language)是一种印度雅利安语，在印度的奥第沙州使用。[奥迪亚文字](https://en.wikipedia.org/wiki/Odia_script)是从卡林加字母发展而来的，卡林加字母是古印度婆罗门文字的众多后裔之一。已知最早的奥迪亚语的例子，在卡林加语中，可以追溯到 1051 年。

> **元音:ଅ ଆ ଇ ଈ ଉ ଊ ଋ ୠ ଏ ଐ ଓ ଔ**
> 
> **辅音：**
> କ ଖ ଗ ଘ ଙ ଚ ଛ ଜ ଝ ଞ ଟ ଠ ଡ ଢ ଣ ତ ତ ଦ ଧ ନ ପ ଫ ବ ଭ ମ ଯ ର ଲ ଳ ଶ ଷ ସ ହ ୟ ୱ
> 
> **数字:**
> ୦ ୧ ୨ ୩ ୪ ୫ ୬ ୭ ୮ ୯

#### 先决条件

在打印字符和数字之前，必须安装`**odia**`库。可以使用`pip`命令安装`odia`库。

```py
pip install odia
```

### 使用 Python 打印 odia 字符

使用`**odia.vowels()**`可以打印 odia 元音，使用`**odia.consonants()**`可以打印 odia 辅音。
**例**:

```py
# Python program to print odia characters

# Import odia library
import odia

# Print vowels
print(odia.vowels)

# print consonants
print(odia.consonants)
```

**输出:**

> ['ଅ', 'ଆ', 'ଇ', 'ଈ', 'ଉ', 'ଊ', 'ଋ', 'ୠ', 'ଏ', 'ଐ', 'ଓ', 'ଔ']
> ['କ', 'ଖ', 'ଗ', 'ଘ', 'ଙ', 'ଚ', 'ଛ', 'ଜ', 'ଝ', 'ଞ', 'ଟ', 'ଠ', 'ଡ', 'ଢ', 'ଣ', 'ତ', 'ଥ', 'ଦ', 'ଧ', 'ନ', 'ପ', 'ଫ', 'ବ', 'ଭ', 'ମ', 'ଯ', 'ୟ', 'ର', 'ଳ', 'ଲ', 'ଵ', 'ଶ', 'ଷ', 'ସ', 'ହ', 'କ୍ଷ', 'ଜ୍ଞ']

**使用 Python 打印 odia 数字**
可以使用`**odia.numbers()**`打印 odia 数字。
**例**:

```py
# Python program to print odia numbers

# Import odia library
import odia

# Print numbers
print(odia.numbers)
```

**输出:**

> [‘日’、‘日’、‘日’、‘日’、‘日’、‘日’、‘日’、‘日’、”