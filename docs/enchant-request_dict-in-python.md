# Python 中的附魔. request_dict()

> 原文:[https://www . geeksforgeeks . org/附魔-request_dict-in-python/](https://www.geeksforgeeks.org/enchant-request_dict-in-python/)

**`Enchant`** 是 python 中的一个模块，用于检查单词的拼写，给出纠正单词的建议。同时，给出了单词的反义词和同义词。它检查字典中是否有一个单词。

## 附魔. request_dict()

**`enchant.request_dict()`** 是`enchant`模块的内置方法。它用于获取特定语言的字典对象。

> **语法:**附魔. request_dict(标记)
> 
> **参数:**
> 标签:语言代码
> 
> **返回:**一个字典对象

**例 1 :**

```py
# import the enchant module
import enchant

# dictionary of en_US
d = enchant.request_dict("en_US")

# the dictionary tag
tag = d.tag
print("The dictionary tag is " + tag)
```

```py
The dictionary tag is en_US

```

**例 2 :** 当执行`enchant.request_dict()`方法时，不传递任何参数，默认取本地机器语言的代码。

```py
# import the enchant module
import enchant

# instantiating the dictionary 
# without passing any parameter
d = enchant.request_dict()

# finding the dictionary tag
tag = d.tag
print("The dictionary tag is " + tag)
```

```py
The dictionary tag is en_IN

```

**示例 3 :** 如果没有合适的字典，则`enchant.request_dict()`方法可能会失败。在这种情况下，将打印以下消息:

```py
enchant.request_dict()
```

**输出:**

> 回溯(最近一次调用最后一次):
> 文件“”，第 1 行，在
> 附魔. request_dict()
> 文件“C:\ user \ user \ AppData \ Local \ Programs \ Python \ Python 37-32 \ lib \ site-packages \附魔\__init__。py”，第 272 行，在 request_dict
> 中返回 Dict(tag，self)
> 文件“C:\ Users \ user \ AppData \ Local \ Programs \ Python \ Python 37-32 \ lib \ site-packages \附魔\__init__。py "，第 541 行，在 _ _ init _ _
> _ 附魔对象中。__init__(self)
> 文件“C:\ user \ user \ AppData \ Local \ Programs \ Python \ Python 37-32 \ lib \ site-packages \附魔\__init__。py "，第 144 行，在 __init__
> self 中。_init_this()
> 文件“C:\ user \ user \ AppData \ Local \ Programs \ Python \ Python 37-32 \ lib \ site-packages \附魔\__init__。py "，第 548 行，in _init_this
> this = self。_ 经纪人。_ request _ dict _ data(self . tag)
> 文件“C:\ user \ user \ AppData \ Local \ Programs \ Python \ Python 37-32 \ lib \ site-packages \附魔\__init__。py "，第 286 行，in _request_dict_data
> self。_raise_error(e_str %(标记，，，DictNotFoundError)
> 文件“C:\ user \ user \ AppData \ Local \ Programs \ Python \ Python 37-32 \ lib \ site-packages \附魔\__init__。py”，第 233 行，in _raise_error
> raise eclass(默认)
> 附魔. enchant.errors.DictNotFoundError:找不到语言“English_India”的词典