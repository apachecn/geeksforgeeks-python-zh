# Python 中的附魔. request_pwl_dict()

> 原文:[https://www . geeksforgeeks . org/附魔-request _ pwl _ dict-in-python/](https://www.geeksforgeeks.org/enchant-request_pwl_dict-in-python/)

**`Enchant`** 是 python 中的一个模块，用于检查单词的拼写，给出纠正单词的建议。同时，给出了单词的反义词和同义词。它检查字典中是否有一个单词。

## 附魔. request_pwl_dict()

**`enchant.request_pwl_dict()`** 是`enchant`模块的内置方法。它用于构建一个自定义词典，也称为个人词表(PSL)。

> **语法:**附魔. request_pwl_dict(text_file)
> 
> **参数:**
> text_file:包含要包含的单词的文本文件的路径，每行一个单词。
> 
> **返回:**一个字典对象

**Example 1:**The contents of the sample file “PWL.txt” are:

> qwerty
> 贾巴
> gfg

```py
# import the enchant module
import enchant

# the path of the text file
file_path = "PWL.txt"

# instantiating the enchant dictionary
# with request_pwl_dict()
pwl = enchant.request_pwl_dict(file_path)

# checking whether the words are
# in the new dictionary
print(pwl.check("gfg"))
```

**输出:**

```py
True
```

**示例 2:** 使用`add()`向 PWL 词典添加新单词。

```py
# import the enchant module
import enchant

# the path of the text file
file_path = "PWL.txt"

# printing the contents of the file
print("File contents:")
with open(file_path, 'r') as f:
    print(f.read())

# instantiating the enchant dictionary
# with request_pwl_dict()
pwl = enchant.request_pwl_dict(file_path)

# the word to be added
new_word = "asd"

# checking whether the word is
# in the dictionary
if pwl.check(new_word):
    print("\nThe word "+ new_word + " exists in the dictionary")
else:
    print("\nThe word "+ new_word + " does not exists in the dictionary")

# addin the word to the dictionary
# using add()
pwl.add("asd")

# printing the contents of the file
# after adding the new word
print("\nFile contents:")
with open(file_path, 'r') as f:
    print(f.read())

# checking for whether the word is
# in the dictionary
if pwl.check(new_word):
    print("The word "+ new_word + " exists in the dictionary")
else:
    print("The word "+ new_word + " does not exists in the dictionary")
```

**输出:**

```py
File contents:
qwerty
jabba
gfg

The word asd does not exists in the dictionary

File contents:
qwerty
jabba
gfg
asd

The word asd exists in the dictionary

```