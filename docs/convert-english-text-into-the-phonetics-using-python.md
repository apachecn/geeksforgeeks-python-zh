# 使用 Python 将英语文本转换为语音

> 原文:[https://www . geesforgeks . org/convert-English-text-in-the-voice-using-python/](https://www.geeksforgeeks.org/convert-english-text-into-the-phonetics-using-python/)

在这篇文章中，我们将看到如何将英语文本转换为[国际音标](https://en.wikipedia.org/wiki/International_Phonetic_Alphabet)。我们将使用 **eng-to-ipa** 模块转换成语音。

**安装:**将此代码运行到您的终端中。

```py
pip install eng-to-ipa 

```

**让我们一步步了解这个模块:**

1.导入此模块，使用 **convert()** 方法将字符串转换为语音。

> **语法:** eng_to_ipa.convert(str)
> 
> **参数:**
> 
> *   **str:** 要转换的文本
> 
> **返回:** IPA 字符串

## 蟒蛇 3

```py
import eng_to_ipa as p

p.convert("Hello Geeks")
```

**输出:**

```py
'hɛˈloʊ giks'

```

2.使用 **ipa_list()** 代替 convert()，它返回每个单词的列表，作为其所有可能的转录的列表。

> **语法:** eng_to_ipa.ipa_list(str)
> 
> **参数:**
> 
> *   **str:** 要转换的文本
> 
> **返回:**所有可能转录的列表。

## 蟒蛇 3

```py
p.ipa_list("Yes i am geeks, How are you")
```

**输出:**

> [[[` a ']、[` e '、` m']、[` giks ']、[` hah ']、[` r '、[` ju ']]

3.****get _ lymps()**方法返回一个单词或一组单词的押韵列表。**

> ****语法:**eng _ to _ IPA . get _ lyms(str)**
> 
> ****参数:****
> 
> *   ****str:** 要押韵的文本**
> 
> ****返回:**一个单词或一组单词的押韵列表。**

## **蟒蛇 3**

```py
p.get_rhymes("Geeks")
```

****输出:****

```py
['antiques',
 'batiks',
 'beeks',
 "belgique's",
 'bespeaks',
 'boutiques',
 'cheeks',
 "creek's",
 'creeks',
 'critiques',
 "deak's",
 'eakes',...
 ......
 .. 
```