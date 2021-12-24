# 如何使用 Python 创建编程语言？

> 原文:[https://www . geesforgeks . org/如何使用 python 创建编程语言/](https://www.geeksforgeeks.org/how-to-create-a-programming-language-using-python/)

在本文中，我们将学习如何使用 SLY(Sly Lex Yacc)和 Python 创建自己的编程语言。在我们深入研究这个主题之前，需要注意的是，这不是初学者教程，您需要了解下面给出的一些先决条件。

#### 先决条件

*   关于编译器设计的粗略知识。
*   基本了解词法分析、解析等编译器设计方面。
*   对正则表达式的理解。
*   熟悉 Python 编程语言。

## 入门指南

为 Python 安装 SLY。SLY 是一个词汇化和解析工具，它让我们的过程变得更加容易。

```py
pip install sly

```

## 打造雷克萨斯

编译器的第一阶段是将所有的字符流(编写的高级程序)转换成标记流。这是通过一个叫做词法分析的过程来完成的。然而，通过使用 SLY 简化了这个过程

首先让我们导入所有必要的模块。

## 蟒蛇 3

```py
from sly import Lexer
```

现在让我们构建一个类*basic xer*，它从 SLY 扩展了 *Lexer* 类。让我们做一个编译器，做简单的算术运算。因此，我们需要一些基本的代币，如*名称*、*号码*、*字符串*。在任何编程语言中，两个字符之间都会有空格。因此，我们创建了一个*忽略*文字。然后我们还创建了像“=”、“+”等基本文字。，*NAME*token 基本上是变量的名称，可以用正则表达式[a-zA-Z_][a-zA-Z0-9_]*来定义。 *STRING* 标记是字符串值，以引号(" ")为界。这可以用正则表达式来定义。*?\".

每当我们找到数字时，我们应该将其分配给令牌*号码*，并且该号码必须存储为整数。我们正在做一个基本的可编程脚本，所以让我们用整数来做，但是，请随意扩展小数、长整型等。，我们也可以发表评论。每当我们找到“//”时，我们会忽略该行中接下来的任何内容。我们用新的行字符做同样的事情。因此，我们已经构建了一个基本的 lexer，它将字符流转换为标记流。

## 蟒 3

```py
class BasicLexer(Lexer):
    tokens = { NAME, NUMBER, STRING }
    ignore = '\t '
    literals = { '=', '+', '-', '/', 
                '*', '(', ')', ',', ';'}

    # Define tokens as regular expressions
    # (stored as raw strings)
    NAME = r'[a-zA-Z_][a-zA-Z0-9_]*'
    STRING = r'\".*?\"'

    # Number token
    @_(r'\d+')
    def NUMBER(self, t):

        # convert it into a python integer
        t.value = int(t.value) 
        return t

    # Comment token
    @_(r'//.*')
    def COMMENT(self, t):
        pass

    # Newline token(used only for showing
    # errors in new line)
    @_(r'\n+')
    def newline(self, t):
        self.lineno = t.value.count('\n')
```

## 构建解析器

首先让我们导入所有必要的模块。

## 蟒 3

```py
from sly import Parser
```

现在让我们构建一个类 *BasicParser* ，它扩展了 *Lexer* 类。来自*基本混合器*的令牌流被传递给变量*令牌。*定义了优先级，这对于大多数编程语言都是一样的。下面程序中编写的大多数解析都非常简单。当什么都没有时，语句什么都不传递。本质上，您可以在键盘上按 enter 键(无需键入任何内容)并进入下一行。接下来，你的语言应该理解使用“=”的作业。这在下面程序的第 18 行处理。当分配给一个字符串时，也可以做同样的事情。

## 蟒 3

```py
class BasicParser(Parser):
    #tokens are passed from lexer to parser
    tokens = BasicLexer.tokens

    precedence = (
        ('left', '+', '-'),
        ('left', '*', '/'),
        ('right', 'UMINUS'),
    )

    def __init__(self):
        self.env = { }

    @_('')
    def statement(self, p):
        pass

    @_('var_assign')
    def statement(self, p):
        return p.var_assign

    @_('NAME "=" expr')
    def var_assign(self, p):
        return ('var_assign', p.NAME, p.expr)

    @_('NAME "=" STRING')
    def var_assign(self, p):
        return ('var_assign', p.NAME, p.STRING)

    @_('expr')
    def statement(self, p):
        return (p.expr)

    @_('expr "+" expr')
    def expr(self, p):
        return ('add', p.expr0, p.expr1)

    @_('expr "-" expr')
    def expr(self, p):
        return ('sub', p.expr0, p.expr1)

    @_('expr "*" expr')
    def expr(self, p):
        return ('mul', p.expr0, p.expr1)

    @_('expr "/" expr')
    def expr(self, p):
        return ('div', p.expr0, p.expr1)

    @_('"-" expr %prec UMINUS')
    def expr(self, p):
        return p.expr

    @_('NAME')
    def expr(self, p):
        return ('var', p.NAME)

    @_('NUMBER')
    def expr(self, p):
        return ('num', p.NUMBER)
```