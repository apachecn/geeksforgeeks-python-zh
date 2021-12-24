# 附魔。Python 中的 Dict()

> 原文:[https://www.geeksforgeeks.org/enchant-dict-in-python/](https://www.geeksforgeeks.org/enchant-dict-in-python/)

**`Enchant`** 是 python 中的一个模块，用于检查单词的拼写，给出纠正单词的建议。同时，给出了单词的反义词和同义词。它检查字典中是否有一个单词。

## 迷人。Dict()

**`enchant.Dict()`** 是`enchant`模块的内置方法。用于创建 Dict 对象，这是`enchant` t 模块中最重要的对象。Dict 对象代表特定语言的字典。

> **语法:**附魔。字典(标签)
> 
> **参数:**
> 标签:语言词典的代码(可选)
> 
> **返回:**一个字典对象

**例 1 :**

```
# import the enchant module
import enchant

# dictionary of en_US
d = enchant.Dict("en_US")

# the dictionary tag
tag = d.tag
print("The dictionary tag is " + tag)
```

```
The dictionary tag is en_US

```

**例 2 :** 当执行`enchant.Dict()`方法时，不传递任何参数，默认取本地机器语言的代码。

```
# import the enchant module
import enchant

# instantiating the dictionary 
# without passing any parameter
d = enchant.Dict()

# finding the dictionary tag
tag = d.tag
print("The dictionary tag is " + tag)
```

```
The dictionary tag is en_IN

```

**示例 3 :** 如果没有合适的字典，则`enchant.Dict()`方法可能会失败。在这种情况下，将打印以下消息:

```
enchant.Dict()
```

**输出:**

> 回溯(最近一次调用最后一次):
> 文件“”，第 1 行，在
> 附魔。Dict()
> 文件“C:\ user \ user \ AppData \ Local \ Programs \ Python \ Python 37-32 \ lib \ site-packages \附魔\__init__。py "，第 541 行，在 _ _ init _ _
> _ 附魔对象中。__init__(自我)
> 文件“C:\ user \ user \ AppData \ Local \ Programs \ Python \ Python 37-32 \ lib \ site-packages \附魔\__init__。py "，第 144 行，在 __init__
> self。_init_this()
> 文件“C:\ user \ user \ AppData \ Local \ Programs \ Python \ Python 37-32 \ lib \ site-packages \附魔\__init__。py "，第 548 行，in _init_this
> this = self。_ 经纪人。_ request _ dict _ data(self . tag)
> 文件“C:\ Users \ user \ AppData \ Local \ Programs \ Python \ Python 37-32 \ lib \ site-packages \附魔\__init__。py "，第 286 行，in _request_dict_data
> self。_raise_error(e_str %(标记，，，DictNotFoundError)
> 文件“C:\ user \ user \ AppData \ Local \ Programs \ Python \ Python 37-32 \ lib \ site-packages \附魔\__init__。py”，第 233 行，in _raise_error
> raise eclass(默认)
> 附魔. enchant.errors.DictNotFoundError:找不到语言“English_India”的词典