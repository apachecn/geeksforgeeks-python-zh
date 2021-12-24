# 附魔。Python 中的 DictWithPWL()

> 哎哎哎:# t0]https://www . geeksforgeeks . org/enchant-dictatwithpwl-in-python/

**`Enchant`** 是 python 中的一个模块，用于检查单词的拼写，给出纠正单词的建议。同时，给出了单词的反义词和同义词。它检查字典中是否有一个单词。

## 很高兴认识你。DictWithPWL()

**`enchant.DictWithPWL()`** 是`enchant`模块的内置方法。它用于组合语言词典和自定义词典，也称为个人词表(PSL)。

> **语法:**附魔。DictWithPWL(标签，文本文件)
> 
> **参数:**
> 标签:语言词典
> text_file 的代码:包含要包含的单词的文本文件的路径，每行一个单词。
> 
> **返回:**一个字典对象

**示例:**

The contents of the sample file “PWL.txt” are:

> qwerty
> 贾巴
> gfg

```
# import the enchant module
import enchant

# dictionary with only en_US
d = enchant.Dict("en_US")

# the word to be searched
word = "gfg"

# check whether the word is in the dictionary
if d.check(word):
    print("The word "+ word + " exists in the dictionary")
else:
    print("The word "+ word + " does not exists in the dictionary")

# the path of the text file
file_path = "PWL.txt"

# instantiating the enchant dictionary
# with DictWithPWL()
d = enchant.DictWithPWL("en_US", file_path)

# checking whether the word is
# in the new dictionary
if d.check(word):
    print("\nThe word "+ word + " exists in the dictionary")
else:
    print("\nThe word "+ word + " does not exists in the dictionary")
```

**输出:**

```
The word gfg does not exists in the dictionary

The word gfg exists in the dictionary

```