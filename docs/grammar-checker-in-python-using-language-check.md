# 使用语言检查的 Python 语法检查器

> 原文:[https://www . geesforgeks . org/python 语法检查器-使用语言-检查/](https://www.geeksforgeeks.org/grammar-checker-in-python-using-language-check/)

Python 是一种开源编程语言。它提供了各种各样的库，提供了更强大的功能。这样的一个库是**语言检查**。语言检查库没有与 Python 3 捆绑在一起。相反，您必须从命令行手动下载或从 pypi.org 下载，然后手动安装。

### 装置

要通过 pip 安装:

```py
$ pip install --upgrade language-check
```

如果您使用 Python 2，您需要预先安装 3to2:

```py
$ pip install --upgrade 3to2
```

### 要求

*   python 3.3+(或 2.7)
*   Java v6.0 或更高版本。

language_check 指定文档中的错误以及规则标识、消息、建议和行号。同样使用这个我们可以直接纠正文件中的错误。它能准确指出错误，但不能保证 100%找到错误。有时它可能会遗漏一些重要的错误。所以完全依赖它是不可取的。

下面的 python 代码演示了对文本文档使用语言检查。

```py
import language_check

# Mention the language keyword
tool = language_check.LanguageTool('en-US')
i = 0

# Path of file which needs to be checked
with open(r'transcript1.txt', 'r') as fin:  

    for line in fin:
        matches = tool.check(line)
        i = i + len(matches)     
        pass

# prints total mistakes which are found 
# from the document
print("No. of mistakes found in document is ", i)
print()

# prints mistake one by one 
for mistake in matches:
    print(mistake)
    print()
```

**输出:**

> 文件中发现的错误数量为 3
> 
> 第 1 行，第 1 列，规则 ID:大写 _ 句子 _START
> 消息:这句话不是以大写字母
> 开头的建议:所以
> 所以如你所见买新车不是…
> ^^
> 
> 第 1 行，第 102 列，规则 ID: ENGLISH_WORD_REPEAT_RULE
> 消息:可能的错别字:您重复了一个单词
> 建议:研究
> ……ing 如果您将遵循三个简单的步骤研究研究研究阅读并找出一切 y……
> ^^^^^^^^^^^^^^^^^
> 
> 第 1 行第 1025 列规则 ID: MORFOLOGIK_RULE_EN_US
> 消息:发现可能的拼写错误
> 建议:语音；规格；规格；斑点；特殊的
> …有趣的方式开始演讲，在特殊和现在使用听众知道我是…