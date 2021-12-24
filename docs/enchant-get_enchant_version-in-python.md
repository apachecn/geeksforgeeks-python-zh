# Python 中的附魔. get _ 附魔 _version()

> 原文:[https://www . geeksforgeeks . org/风魔-get _ 风魔 _ python 中的版本/](https://www.geeksforgeeks.org/enchant-get_enchant_version-in-python/)

**`Enchant`** 是 python 中的一个模块，用于检查单词的拼写，给出纠正单词的建议。同时，给出了单词的反义词和同义词。它检查字典中是否有一个单词。

## 附魔. get _ 附魔 _version()

**`enchant.get_enchant_version()`** 是`enchant`模块的内置方法。用于查看系统正在使用的`enchant`模块版本。

> **语法:**附魔. get _ 附魔 _version()
> 
> **参数:**无
> 
> **返回:**一个包含`enchant` 版本的字符串

**例 1 :**

```py
# import the enchant module
import enchant

# printing the version
print(enchant.get_enchant_version())
```

**输出:**

```py
2.2.7
```

**例 2 :** 附魔模块的版本也可以使用`help()`方法找到。

```py
# import the enchant module
import enchant

# using the help() method
help(enchant)
```

**输出:**实际输出 574 行。这里只显示包含版本的最后几行。

> set_prefix_dir(路径)
> 设置附魔库查找插件时使用的前缀
> 
> 当需要
> 时导入 Python 库时自动调用。
> 
> 版本
> 2.2.7
> 
> FILE
> c:\ user \ user \ app data \ local \ programs \ python \ python 37-32 \ lib \ site-packages \附魔\__init__。巴拉圭