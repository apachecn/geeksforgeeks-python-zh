# 附魔. dict_exists()在 Python 中

> 原文:[https://www . geeksforgeeks . org/附魔-dict_exists-in-python/](https://www.geeksforgeeks.org/enchant-dict_exists-in-python/)

**`Enchant`** 是 python 中的一个模块，用于检查单词的拼写，给出纠正单词的建议。同时，给出了单词的反义词和同义词。它检查字典中是否有一个单词。

## 附魔. dict_exists()

**`enchant.dict_exists()`** 是`enchant`模块的内置方法。它用于检查特定语言词典的可用性。

> **语法:**附魔. dict_exists(标签)
> 
> **参数:**
> 标签:字符串数据类型的语言字典的代码
> 
> **返回:**一个布尔值，如果字典存在则为真，如果不存在则为假

**Example 1:** When `enchant.dict_exists()` returns True.

```
# import the enchant module
import enchant

# American English dictionary
tag = "en_US"

# check whether American English(en_US) 
# dictionary exists or not
exists = enchant.dict_exists(tag)
if exists == True:
    print("The dictionary for " + tag + " exists.")
else:
    print("The dictionary for " + tag + " does not exists.")
```

**输出:**

```
The dictionary for en_US exists.
```

**例 2:** 当`enchant.dict_exists()`返回假时。

```
# import the enchant module
import enchant

# Hindi dictionary
tag = "hi_IN"

# check whether Hindi(hi_IN) 
# dictionary exists or not
exists = enchant.dict_exists(tag)
if exists == True:
    print("The dictionary for " + tag + " exists.")
else:
    print("The dictionary for " + tag + " does not exists.")
```

**输出:**

```
The dictionary for hi_IN does not exists.
```