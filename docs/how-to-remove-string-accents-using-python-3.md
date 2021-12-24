# 如何用 Python 3 去除字符串重音？

> 原文:[https://www . geesforgeks . org/如何使用-python-3/](https://www.geeksforgeeks.org/how-to-remove-string-accents-using-python-3/) 移除字符串重音

字符串重音是从其他重音语言改编而来的特殊字符串。在本文中，我们将从字符串中移除升阶。

**示例:**

> **输入:**orpás’d
> 
> **输出:** orcpzsiayd
> 
> **输入:**杆
> 
> **输出:**斯塔万格

我们可以通过使用名为 *Unidecode 的 Python 模块来移除字符串中的重音符号。该模块由*方法组成，该方法接受一个 Unicode 对象或字符串，并返回一个没有扩展名的字符串。**

***语法:***

> *output _ string = unide code . unide code(target _ string)*

***以下是一些描述如何从字符串中移除升序的示例:***

***例 1:***

## *蟒蛇 3*

```py
*# import required module
import unidecode

# assign string
string = "orčpžsíáýd"

# display original string
print('\nOriginal String:', string)

# remove ascents
outputString = unidecode.unidecode(string)

# display new string
print('\nNew String:', outputString)*
```

***输出:***

```py
*Original String: orčpžsíáýd

New String: orcpzsiayd*
```

***例 2:***

## *蟒蛇 3*

```py
*# import required module
import unidecode

# assign string
string = "stävänger"

# display original string
print('\nOriginal String:', string)

# remove ascents
outputString = unidecode.unidecode(string)

# display new string
print('\nNew String:', outputString)*
```

***输出:***

```py
*Original String: stävänger

New String: stavanger*
```

***例 3:***

## *蟒蛇 3*

```py
*# import required module
import unidecode

# assign string
stringList = ["hell°",  "tromsø",  "stävänger", "ölut"]

# display original string
print('\nOriginal List of Strings:\n', stringList)

for i in range(len(stringList)):
    # remove ascents
    stringList[i] = unidecode.unidecode(stringList[i])

# display new string
print('\nNew List of Strings:\n', stringList)*
```

***输出:***

```py
*Original List of Strings:
 ['hell°', 'tromsø', 'stävänger', 'ölut']

New List of Strings:
 ['helldeg', 'tromso', 'stavanger', 'olut']*
```