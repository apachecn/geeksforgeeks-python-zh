# Python 中的模式匹配与 Regex

> 原文:[https://www . geesforgeks . org/pattern-matching-python-regex/](https://www.geeksforgeeks.org/pattern-matching-python-regex/)

先决条件:[Python 中的正则表达式](https://www.geeksforgeeks.org/regular-expression-python-examples-set-1/)

您可能熟悉通过按 ctrl-F 并键入您要查找的单词来搜索文本。正则表达式更进一步:它们允许您指定要搜索的文本模式。
正则表达式，简称 regexes，是对文本模式的描述。例如，正则表达式中的 a \d 代表一个数字字符，即从 0 到 9 的任何单个数字。

*   Python 中使用了以下正则表达式来匹配由三个数字、一个连字符、三个数字、另一个连字符和四个数字组成的字符串。

    ```
    Any other string would not match the pattern.
    \d\d\d-\d\d\d-\d\d\d\d
    ```

*   Regular expressions can be much more sophisticated. For example, adding a 3 in curly brackets ({3}) after a pattern is like saying, “ Match this pattern three times.” So the slightly shorter regex

    ```
    \d{3}-\d{3}-\d{4}
    ```

    (它匹配正确的电话号码格式。)

**创建正则表达式对象**

Python 中的所有正则表达式函数都在 re 模块中

```
import re
```

要创建与电话号码模式匹配的 Regex 对象，请在交互式外壳中输入以下内容。

```
phoneNumRegex = re.compile(r'\d\d\d-\d\d\d-\d\d\d\d')
```

现在 phoneNumRegex 变量包含一个 Regex 对象。

**匹配正则表达式对象**

regex 对象的 search()方法在传递给它的字符串中搜索与 Regex 匹配的任何内容。Match 对象有一个 group()方法，该方法将从搜索到的字符串中返回实际匹配的文本。

```
# Python program to illustrate
# Matching regex objects
import re
phoneNumRegex = re.compile(r'\d\d\d-\d\d\d-\d\d\d\d')
mo = phoneNumRegex.search('My number is 415-555-4242.')
print('Phone number found: ' + mo.group())
```

输出:

```
Phone number found: 415-555-4242
```

**正则表达式匹配的步骤**

虽然在 Python 中使用正则表达式有几个步骤，但每个步骤都相当简单。

1.  使用导入 re 导入 regex 模块。
2.  使用 re.compile()函数创建一个 Regex 对象。(记得使用原始字符串。)
3.  将要搜索的字符串传递到 Regex 对象的 search()方法中。这将返回一个匹配对象。
4.  Call the Match object’s group() method to return a string of the actual matched text.

    **括号分组**

    1.  **Matching objects:**Say you want to separate the area code from the rest of the phone number. Adding parentheses will create groups in the regex: (\d\d\d)-(\d\d\d-\d\d\d\d). Then you can use the group() match object method to grab the matching text from just one group.

        ```
        # Python program to illustrate
        # Matching regex objects
        # with grouping 
        import re
        phoneNumRegex = re.compile(r'(\d\d\d)-(\d\d\d-\d\d\d\d)')
        mo = phoneNumRegex.search('My number is 415-555-4242.')
        print(mo.group(1))
        ```

        输出:

        ```
        '415'

        ```

    2.  **Retrieve all the groups at once :** If you would like to retrieve all the groups at once, use the groups(), method—note the plural form for the name.

        ```
        # Python program to illustrate
        # Matching regex objects
        # with groups 
        import re
        phoneNumRegex = re.compile(r'(\d\d\d)-(\d\d\d-\d\d\d\d)')
        mo = phoneNumRegex.search('My number is 415-555-4242.')
        print(mo.groups())
        ```

        输出:

        ```
        ('415', '555-4242')
        ```

    3.  **Using mo.groups :** mo.groups() will return a tuple of multiple values, you can use the multiple-assignment trick to assign each value to a separate variable, as in the following areaCode, mainNumber = mo.groups() line.

        ```
        # Python program to illustrate
        # Matching regex objects
        # with mo.groups() 
        import re
        phoneNumRegex = re.compile(r'(\d\d\d)-(\d\d\d-\d\d\d\d)')
        mo = phoneNumRegex.search('My number is 415-555-4242.')
        areaCode, mainNumber = mo.groups()
        print(mainNumber)
        ```

        输出:

        ```
        '555-4242'
        ```

    4.  **Match a parenthesis :** Parentheses have a special meaning in regular expressions, but what do you do if you need to match a parenthesis in your text. For instance, maybe the phone numbers you are trying to match have the area code set in parentheses. In this case, you need to escape the ( and ) characters with a backslash. Enter the following into the interactive shell:

        ```
        # Python program to illustrate
        # Matching regex objects
        # with grouping 
        import re
        phoneNumRegex = re.compile(r'(\(\d\d\d\)) (\d\d\d-\d\d\d\d)')
        mo = phoneNumRegex.search('My phone number is (415) 555-4242.')
        print(mo.group(1))
        ```

        输出:

        ```
        '(415)'
        ```

        传递给 re.compile()的原始字符串中的\(和\)转义字符将与实际的括号字符匹配。

**用管道匹配多个组**

字符|被称为管道。你可以在任何你想匹配的地方使用它。例如，正则表达式“蝙蝠侠|蒂娜·菲”将匹配“蝙蝠侠”或“蒂娜·菲”。

当搜索到的字符串中同时出现蝙蝠侠和蒂娜·菲时，第一个匹配文本将作为匹配对象返回。在交互式外壳中输入以下内容:

```
# Python program to illustrate
# Matching regex objects
# with multiple Groups with the Pipe
import re
heroRegex = re.compile (r'Batman|Tina Fey')
mo1 = heroRegex.search('Batman and Tina Fey.')
print(mo1.group())
```

输出:

```
'Batman'
```

**用花括号匹配特定重复**

如果您有一个要重复特定次数的组，请在正则表达式中的组后面加上一个花括号中的数字。例如，正则表达式(Ha){3}将匹配字符串“哈哈哈”，但不会匹配“哈哈”，因为后者只有(Ha)组的两个重复。

您可以通过在花括号之间写入最小值、逗号和最大值来指定一个范围，而不是一个数字。例如，正则表达式(哈){3，5}将匹配“哈哈哈”、“哈哈哈”和“哈哈哈哈”。

您也可以省略花括号中的第一个或第二个数字，使最小或最大值不受限制。例如，(Ha){3，}将匹配(Ha)组的三个或更多实例，而(Ha){，5}将匹配零到五个实例。花括号有助于缩短正则表达式。这两个正则表达式匹配相同的模式:

```
(Ha){3}
(Ha)(Ha)(Ha)
```

这两个正则表达式也匹配相同的模式:

```
(Ha){3, 5}
((Ha)(Ha)(Ha))|((Ha)(Ha)(Ha)(Ha))|((Ha)(Ha)(Ha)(Ha)(Ha))
```

在交互式外壳中输入以下内容:

```
# Python program to illustrate
# Matching Specific Repetitions 
# with Curly Brackets
import re
haRegex = re.compile(r'(Ha){3}')
mo1 = haRegex.search('HaHaHa')
print(mo1.group())
```

输出:

```
'HaHaHa'
```

```
# Python program to illustrate
# Matching Specific Repetitions 
# with Curly Brackets
import re
haRegex = re.compile(r'(Ha){3}')
mo2 = haRegex.search('Ha')== None
print(mo2)
```

输出:

```
True

```

这里，(哈){3}匹配“哈哈哈”但不匹配“哈”。由于它与“哈”不匹配，搜索()返回“无”。

**可选匹配问号**

有时有一种模式，你想匹配只是可选的。也就是说，正则表达式应该找到一个匹配，不管那一段文本是否存在。**那个？**字符将它前面的组标记为模式的可选部分。例如，在交互式外壳中输入以下内容:

```
# Python program to illustrate
# optional matching
# with question mark(?)
import re
batRegex = re.compile(r'Bat(wo)?man')
mo1 = batRegex.search('The Adventures of Batman')
print(mo1.group())
```

输出:

```
'Batman'
```

```
# Python program to illustrate
# optional matching
# with question mark(?)
import re
batRegex = re.compile(r'Bat(wo)?man')
mo2 = batRegex.search('The Adventures of Batwoman')
print(mo2.group())
```

输出:

```
'Batwoman'
```

那个(wo)？正则表达式的一部分意味着模式 wo 是可选组。正则表达式将匹配零个实例或一个 wo 实例的文本。这就是正则表达式同时匹配“蝙蝠女侠”和“蝙蝠侠”的原因。
你能想到的？俗话说，**“匹配这个问号前面的零个或一个组。”**
如果需要匹配一个实际的问号字符，用\？。

**将零或更多与星匹配**

*(称为星号或星号)表示“匹配零个或多个”——星号前面的组可以在文本中出现任意多次。它可以完全不存在，也可以反复出现。我们再来看看蝙蝠侠的例子。

```
# Python program to illustrate
# matching a regular expression
# with asterisk(*)
import re
batRegex = re.compile(r'Bat(wo)*man')
mo1 = batRegex.search('The Adventures of Batman')
print(mo1.group())
```

输出:

```
'Batman'
```

```
#python program to illustrate
#matching a regular expression
#with asterisk(*)
import re
batRegex = re.compile(r'Bat(wo)*man')
mo2 = batRegex.search('The Adventures of Batwoman')
print(mo2.group())
```

输出:

```
'Batwoman'
```

```
# Python program to illustrate
# matching a regular expression
# with asterisk(*)
import re
batRegex = re.compile(r'Bat(wo)*man')
mo3 = batRegex.search('The Adventures of Batwowowowoman')
print(mo3.group())
```

输出:

```
'Batwowowowoman'
```

对于“Batman”，正则表达式的(wo)*部分匹配字符串中 wo 的零个实例；对于“蝙蝠女侠”，则(wo)*匹配 wo 的一个实例；而对于‘batwowowowowoman’，(wo)*匹配 wo 的四个实例。

如果需要匹配实际的星号字符，请在正则表达式中的星号前加一个反斜杠\*。

**用加号匹配一个或多个**

而*表示“匹配零个或多个”，则+(或加号)表示**“匹配一个或多个”**与不要求其组出现在匹配字符串中的星号不同，加号前的组必须至少出现一次。它不是可选的。在交互式 shell 中输入以下内容，并将其与上一节中的 star regexes 进行比较:

```
# Python program to illustrate
# matching a regular expression
# with plus(+)
import re
batRegex = re.compile(r'Bat(wo)+man')
mo1 = batRegex.search('The Adventures of Batwoman')
print(mo1.group())
```

输出:

```
'Batwoman'
```

```
# Python program to illustrate
# matching a regular expression
# with plus(+)
import re
batRegex = re.compile(r'Bat(wo)+man')
mo2 = batRegex.search('The Adventures of Batwowowowoman')
print(mo2.group())
```

输出:

```
'Batwowowowoman'
```

batRegex = re . compile(r ' Bat(wo)+man ')

```
# Python program to illustrate
# matching a regular expression
# with plus(+)
import re
batRegex = re.compile(r'Bat(wo)+man')
mo3 = batRegex.search('The Adventures of Batman')== None
print(mo3)
```

输出:

```
True
```

regex Bat(wo)+man 不会匹配字符串“蝙蝠侠历险记”，因为加号至少需要一个 wo。

如果需要匹配实际的加号字符，请在加号前加一个反斜杠来转义它:\+。

本文由 **Shubham Machal** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。