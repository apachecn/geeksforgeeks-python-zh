# Python 中的附魔. list_languages()

> 原文:[https://www . geeksforgeeks . org/附魔-list_languages-in-python/](https://www.geeksforgeeks.org/enchant-list_languages-in-python/)

**`Enchant`** 是 python 中的一个模块，用于检查单词的拼写，给出纠正单词的建议。同时，给出了单词的反义词和同义词。它检查字典中是否有一个单词。

## 附魔. dict_exists()

**`enchant.list_languages()`** 是`enchant`模块的内置方法。它用于列出字典可用的语言。

> **语法:**附魔.列表 _ 语言()
> 
> **参数:**无
> 
> **返回:**字典可用的语言代码列表

**Example 1:**

```
# import the enchant module
import enchant

# list the languages for which
# dictionaries are available
print(enchant.list_languages())
```

**输出:**

> [' en _ bw '，' en_AU '，' en_BZ '，' en_GB '，' en_JM '，' en_DK '，' en_GH '，' en_US '，' en_ZA '，' en_ZW '，' en_SG '，' en_NZ '，' en_BS '，' en_AG '，' en_PH '，' en_IE '，' en_NA '，' en_TT '，' en_NG '，' en _ ca ']

**示例 2:** 验证所有由`enchant.list_languages()`生成的语言代码是否存在于`enchant`中或者不使用`enchant.dict_exists()`。

```
# import the enchant module
import enchant

for lang in enchant.list_languages():
    if enchant.dict_exists(lang):
        print("The dictionary for " + lang + " exists.")
    else:
        print("The dictionary for " + lang + " does not exists.")
```

**输出:**

> en_BW 的字典已存在。
> en _ AU 的字典存在。
> en _ BZ 的字典存在。
> en _ GB 的字典已经存在。
> 恩 JM 的字典是存在的。
> en _ DK 的字典存在。
> en _ HK 的字典存在。
> en _ GH 的字典存在。
> en _ US 的字典存在。
> en _ ZA 的字典存在。
> en _ ZW 的字典存在。
> en _ SG 的字典存在。
> en _ NZ 的字典存在。
> en _ BS 的字典存在。
> en _ AG 的字典存在。
> en _ PHS 的字典存在。
> en _ IE 的字典存在。
> en _ NA 的字典存在。
> TT 的字典是存在的。
> en _ IN 的字典存在。
> en _ NG 的字典存在。
> en _ CA 的字典存在。