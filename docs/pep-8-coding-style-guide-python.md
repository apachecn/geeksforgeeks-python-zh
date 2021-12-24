# PEP 8:Python 中的编码风格指南

> 原文:[https://www . geesforgeks . org/pep-8-编码-风格-指南-python/](https://www.geeksforgeeks.org/pep-8-coding-style-guide-python/)

实际上，编码和应用逻辑是任何编程语言的基础，但是还有一个因素是每个编码者在编码时必须记住的，那就是编码风格。牢记这一点，Python 保持了严格的脚本顺序和格式。遵循这一点有时是强制性的，对用户来说是一个很大的帮助。让其他人更容易阅读代码总是一个好主意，采用一种好的编码风格对此有很大帮助。

对于 Python 来说， **PEP 8** 已经成为大多数项目坚持的风格指南；它提倡一种可读性很强、赏心悦目的编码风格。每个 Python 开发人员都应该在某个时候阅读它；以下是为您提取的最重要的要点:

**1。使用 4 个空格的缩进，没有制表符。**
例:

```
# Aligned with opening delimiter.
grow = function_name(variable_one, variable_two,
                     variable_three, variable_four)

```

```
# First line contains no argument. Second line onwards
# more indentation included to distinguish this from 
# the rest.
def function_name(
        variable_one, variable_two, variable_three,
        variable_four):
    print(variable_one)

```

4 空格规则并不总是强制性的，对于延伸线可以否决。

**2。使用文档字符串:**Python 中既可以使用单行文档字符串，也可以使用多行文档字符串。但是，单行注释放在一行中，两种情况下都使用三重引号。这些用于定义特定的程序或特定的功能。
例:

```
def exam():
    """This is single line docstring"""

    """This is
    a
    multiline comment"""

```

**3。换行不要超过 79 个字符:**Python 标准库比较保守，要求行数限制在 79 个字符以内。可以使用括号、括号和大括号来包装行。它们应该优先于反斜杠使用。
例:

```
with open('/path/from/where/you/want/to/read/file') as file_one, \
     open('/path/where/you/want/the/file/to/be/written', 'w') as file_two:
    file_two.write(file_one.read())

```

**4。使用定期更新的评论对程序员和用户来说都是有价值的**:从程序和用户的角度来看，还有各种各样的类型和条件，如果遵循的话会有很大的帮助。注释应该形成完整的句子。如果注释是一个完整的句子，它的第一个单词应该大写，除非它是一个以小写字母开头的标识符。简而言之，末尾的句号可以省略。在块注释中，有多个段落，每个句子必须以句点结尾。块注释和内联注释可以写在单个“#”后面。
内嵌注释示例:

```
geek = geek + 1                 # Increment

```

**5。使用尾随逗号:**这不是强制性的，除非在创建元组时。
例:

```
tup = ("geek",)

```

5.**使用 Python 默认的 *UTF-8* 或 *ASCII* 编码，而不是任何花哨的编码**，如果它是为国际环境准备的话。

**6。在运算符周围和逗号后面使用空格，但不要直接放在包围结构内:**

```
a = f(1, 2) + g(3, 4)
```

**7。命名约定:**为了使程序不那么复杂，可读性更强，应该遵循的命名约定很少。同时，Python 中的命名约定有点混乱，但这里有几个约定可以轻松遵循。
有一个压倒一切的原则，即作为 API 公共部分的用户可见的名称应该遵循反映用法而不是实现的约定。
以下是一些其他的命名约定:

```
b (single lowercase letter)

B (single upper case letter)

lowercase

lower_case_with_underscores

UPPERCASE

UPPER_CASE_WITH_UNDERSCORES

CapitalizedWords (or CamelCase). This is also sometimes known as StudlyCaps.
Note: While using abbreviations in CapWords, capitalize all the letters 
of the abbreviation. Thus HTTPServerError is better than HttpServerError.

mixedCase (differs from CapitalizedWords by initial lowercase character!)

Capitalized_Words_With_Underscores
```

除了这几个，前导或尾随下划线也被考虑。
例:
**单 _ 前导 _ 下划线:**弱“内部使用”指标。例如从 M 导入*不导入名称以下划线开头的对象。

**single _ trading _ 下划线 _:** 用于避免与 Python 关键字冲突。
例:

```
Tkinter.Toplevel(master, class_='ClassName')
```

**_ _ double _ leading _ 下划线:**命名类属性时，调用名称 mangling。
(类 FooBar 里面，__boo 变成了 _ FooBar _ _ boo).

**_ _ double _ leading _ and _ trading _ 下划线 __:** “神奇”的对象或属性存在于用户控制的命名空间中。例如 *__init__、__import__ 或 __file__* 。仅在有记录的情况下使用它们。

**8。不应用于标识符的字符:**‘l’(小写字母 el)、‘O’(大写字母 oh)或‘I’(大写字母 eye)作为单字符变量名，因为这些类似于数字 1 和 0。

**9。如果说不同语言的人阅读或维护代码的可能性极小，不要在标识符**中使用非 ASCII 字符。
 **10。一致地命名你的类和函数:**惯例是类使用 **CamelCase** ，函数和方法使用**lower _ case _ with _ 下划线**。始终使用 **self** 作为第一个方法参数的名称。

**11 时。在命名方法的函数时，总是使用 *self* 作为实例方法的第一个参数**，使用 *cls* 作为类方法的第一个参数。如果一个函数的参数名与保留字匹配，那么它可以用一个尾随的逗号来写。例如，对于类 _

您可以参考这个简单的程序来了解如何编写可理解的代码:

```
# Python program to find the
# factorial of a number provided by the user. 

# change the value for a different result 
num = 7

# uncomment to take input from the user 
#num = int(input("Enter a number: ")) 

factorial = 1

# check if the number is negative, positive or zero 
if num < 0: 
    print("Sorry, factorial does not exist for negative numbers") 
elif num == 0: 
    print("The factorial of 0 is 1") 
else: 
    for i in range(1,num + 1): 
        factorial = factorial*i 

print("The factorial of",num,"is",factorial) 
```

**输出:**

```
The factorial of 7 is 5040

```

本文由**钦莫伊·蕾恩卡**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。