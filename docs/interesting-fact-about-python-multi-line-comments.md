# 关于 Python 多行注释的有趣事实

> 原文:[https://www . geesforgeks . org/interest-fact-about-python-多行-注释/](https://www.geeksforgeeks.org/interesting-fact-about-python-multi-line-comments/)

**多行注释**(注释块)用于在**调试应用程序**时描述大文本代码或注释掉大块代码。
**Python 支持多行注释吗(比如 c/c++……)？**
其实在很多在线教程和网站中你会发现 multiline_comments 在 python 中是可用的(“”或者“’)。不过我们先来看看 python 创作者是怎么说的，《吉多·范·罗苏姆》说的关于假块的评论风格:
**Python 提示:**你可以用多行字符串作为多行评论。除非用作[文档字符串](https://www.geeksforgeeks.org/python-docstrings/)，否则不生成代码！。
[源文件](https://twitter.com/gvanrossum/status/112670605505077248)

*   如果用单行书写文本，那么在 python 中使用双引号或单引号。
*   如果写一首诗或歌曲或多行文字，那么要用三重引号(“”或“’)。
*   如果打印这些行或文本，只需将其插入 print()函数。

**示例:**

## 蟒蛇 3

```py
# Write Python3 code here
#this is only valid for single line

"this is a text constant for single line you"
"can't use multi-line within single or double quotes"

'this is also text-constant for single line'

#this is valid for multiline.
"""this is text constant for multi
or single line this will not
give any error"""

#you can also print both look at below..
print('this is also text-constant for single line')
print("""this is text constant for mult-line
or single line this will not
give any error""")
```

上述技术不会创建真正的注释。它只是插入不会改变任何东西的文本常量，或者说这是代码中某处的常规单行字符串。请始终记住正确缩进第一个(**“”或“**)匹配，否则会生成语法错误。
T3】例:

## 蟒蛇 3

```py
# Write Python3 code here
def check_syntax():
    """
    look at your first ident
    below"""
print("after this line interpreter gives error because your first ident doesnot match")
 """ <---- here first ident starts with 2nd column hence gives indentation error you must remember that  your first ident must be correctly  matched.
"""
```

**我们如何轻松注释掉大块代码？**
只需选择那些行(意思是什么时候复制文本，然后先选择那些行)，然后按(cntrl+#)否则每一行中连续的#是唯一的方法。
T4【总结:

*   与其他编程语言(c、c++、…)不同，“python”不支持开箱即用的多行注释块
*   可以将三倍引号“”视为多行注释，但这不是一个好主意，因为这种类型的注释行可能会变成意外的文档字符串。
*   continuous #是 python 中注释行的唯一方法(如果要注释多行，可以选择这些行，然后在 python3 中按(ctrl+#)。