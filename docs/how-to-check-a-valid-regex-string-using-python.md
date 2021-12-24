# 如何使用 Python 检查有效的正则表达式字符串？

> 原文:[https://www . geesforgeks . org/how-to-check-a-valid-regex-string-use-python/](https://www.geeksforgeeks.org/how-to-check-a-valid-regex-string-using-python/)

A **Regex (** ***正则表达式*** **)** 是用于定义模式的字符序列。这种模式可以用于搜索、替换和其他操作。Regex 广泛应用于需要输入验证、密码验证、模式识别、搜索和替换实用程序(可在文字处理器中找到)等的应用程序中。这是因为 regex 语法在不同的编程语言和实现中保持不变。因此，一个人掌握了它，就能在不同的语言中长寿。在本文中，我们将创建一个程序来检查正则表达式字符串的有效性。

我们将要使用的方法需要对 python 的*尝试有一个坚定的理解。因此，如果我们在进入实际代码之前触及这一点，那将是明智的。*

## **异常处理**

Try except block 用于捕获和处理特定代码块执行过程中遇到的异常(构造存在于其他编程语言中，名为 *try-catch* )。*try-除了*块的一般语法如下:

> **尝试:**
> 
> #执行这段代码
> 
> 。
> 
> 。
> 
> **除** ***【例外】*** **:**
> 
> #如果在执行 try 块的过程中出现异常，请执行此代码
> 
> 。
> 
> 。

在上面的语法中，在 try 块中找到的任何代码都将被执行。如果在执行 try 块期间出现异常/错误，则(仅)执行 except 块。如果 try 块执行时没有产生异常，那么 except 块将不会被执行。如果使用了一个空的 except 子句，那么它将捕获在执行 try block 期间遇到的任何异常(甚至某些*System _ exists*)。为了防止这种情况发生，通常最好在 except 之后指定一个异常。这确保了只有在遇到特定的异常/错误之后，才会执行 except 块。这可以防止隐藏在执行 try 块期间遇到的其他错误。此外，在同一个 try-except 块中可以使用多个 except 子句，这使得它能够捕获过多的异常，并专门处理它们。该结构还包含其他关键字，如 finally、else 等。这在当前环境中是不需要的。因此，仅描述相关部分。

**代码:**

在下面的代码中，我们将指定 *re.error* 作为 try-except 块的 except 子句中的异常。在模式编译期间，当发现无效的 regex 模式时，会遇到此错误。

T5】蟒 3T7

```
import re

# pattern is a string containing the regex pattern
pattern = r"[.*"

try:
    re.compile(pattern)

except re.error:
    print("Non valid regex pattern")
    exit()
```

T8T10**输出**T1

**说明:**

首先，我们导入了 re 库，以便在代码中启用 regex 功能。然后，我们将包含正则表达式模式的字符串分配给变量模式。提供的模式无效，因为它包含未关闭的字符类(在正则表达式中，方括号`[ ]'用于定义字符类)。我们将 *re.compile()* (用于编译正则表达式模式)函数放在 try 块中。这将首先尝试编译模式，如果在编译过程中出现任何异常，它将首先检查它是否是 *re.error* ，如果是，则只有 except 块将执行。否则，异常将显示在回溯中，导致程序终止。except 块包含打印语句，该语句将用户定义的消息输出到 stdout，然后退出程序(通过*退出()*)。由于提供的模式是无效的(前面已经解释过)，这将导致 except 块被执行。

**注:**

以上代码只处理 *re.error* 异常。但是与正则表达式相关的其他异常也存在，例如*递归错误*，这需要具体处理(也可以通过为该异常添加一个单独的 except 子句，或者在这种情况下使用 *sys.setrecursionlimit()* 更改最大堆栈深度)。

## **检查输入字符串是否匹配 Regex 模式**

在下面的示例中，我们将测试输入字符串是否匹配给定的正则表达式模式。这是假设正则表达式模式是有效的(可以使用前面提到的例子来确保)。我们将检查输入字符串是否是字母数字字符串(包含字母或数字的字符串)。我们将使用以下类来检查字符串:

```
^[A-Za-z0-9]+$
```

即使正则表达式中存在一个特殊的序列来查找字母数字字符。但是我们不会使用它，因为它在其字符类(A-Za-z0-9 **_** )中包含下划线(_)，这在大多数标准下不被认为是字母数字字符。

**代号:**

## 蟒 3

```
import re

# compiling the pattern for alphanumeric string
pat = re.compile(r"[A-Za-z0-9]+")

# Prompts the user for input string
test = input("Enter the string: ")

# Checks whether the whole string matches the re.pattern or not
if re.fullmatch(pat, test):
    print(f"'{test}' is an alphanumeric string!")
else:
    print(f"'{test}' is NOT a alphanumeric string!")
```

**输出:**

```
> Enter the string: *DeepLearnedSupaSampling01*
  'DeepLearnedSupaSampling01' is an alphanumeric string!
```

```
> Enter the string: *afore 89df*
  'afore 89df' is NOT a alphanumeric string!
```

**说明:**

首先，我们使用 *re.compile()* 编译正则表达式模式。Regex 模式包含一个字符集，用于指定模式中包括所有字母(小写和大写)和数字(0-9)。类后面是加号(+)，它是一个重复限定词。这允许结果正则表达式搜索匹配前面正则表达式的一个或多个重复(对我们来说是字母数字字符集)。然后我们提示用户输入字符串。之后，我们将输入字符串和编译后的正则表达式模式传递给 *re.fullmatch()* 。此方法检查整个字符串是否匹配正则表达式模式。如果是，则返回 1，否则返回 0。我们在 *if-else* 构造中使用它来相应地显示成功/失败消息。