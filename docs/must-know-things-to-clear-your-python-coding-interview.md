# 清理 Python 编码面试必须知道的事情

> 原文:[https://www . geesforgeks . org/必须知道的事情-清除你的 python-编码-面试/](https://www.geeksforgeeks.org/must-know-things-to-clear-your-python-coding-interview/)

Python 不仅是最受欢迎的语言之一，而且被用于各种不同的领域。由于它在很多领域的高度依赖和使用，Python 编程语言和相关框架的职位空缺突然增加。Python 开发人员需求量很大，因为它可以毫不费力地解决网络开发、数据科学、人工智能、云计算和网络安全等领域的问题。2021 年，Python 开发人员的职位空缺大幅增加。

![Things-That-You-Must-Know-to-Clear-Your-Python-Coding-Interview](img/500a08a9a3c116f901fcc0c07ff8d587.png)

因此，担任 Python 角色不仅意味着你必须擅长 Python 库、模块和数据结构，还意味着你必须能够在没有冗余代码的情况下编写干净的代码。这意味着 Python 已经提供了很多内置的方法和库，这样就不必编写冗长的冗余代码。让我们一个一个来看，这样你就可以完美地清除你的 Python 面试了！

### 1.Python 中的字符串格式

Python 使用类似于 C 语言的字符串格式来创建新的格式化字符串。要在代码中灌输字符串格式，有三种方法可以实现它:借助占位符，使用 format()方法，以及使用字符串文字(即 f-strings)进行格式化。使用占位符方法时，我们需要将模(%)运算符与 *s，d，f* 或 *b* 字符一起使用，其中 *s* 表示插入字符串， *d* 表示插入十进制值， *f* 表示浮点值， *b* 表示插入二进制值。当使用 format()方法时，我们需要传入字符串值作为要在原始字符串中替换的参数。它还可以在实际字符串中使用索引插入多个值。Python 3.6 及更高版本中引入了使用 f 字符串的最后一种方法。这里，我们将原始字符串附加到字符 *f* 上，然后将变量放在花括号中的字符串内。

要了解更多信息，请阅读:[**Python 中的字符串格式**](https://www.geeksforgeeks.org/string-formatting-in-python/)

### 2.使用生成器而不是列表理解

使用列表理解在处理较小的列表时非常有用。如果列表理解用于更大的列表，它通常会消耗大量的时间，从而减慢你的程序。因此，Python 提供了帮助创建自己的迭代器函数的生成器。这是一种特殊类型的 Python 函数，它不是提供单个值，而是为迭代器对象提供一系列值。在正常函数中，我们使用*返回*关键字，但是在生成器函数中，我们使用 [***产生*** **关键字**](https://www.geeksforgeeks.org/python-yield-keyword/) 。 *return* 语句终止函数，而 *yield* 仅暂停执行，同时保持函数的内部状态。

要了解更多信息，必须阅读:[**Python 中的生成器**](https://www.geeksforgeeks.org/generators-in-python/)

### 3.枚举()方法的魔力

我们都使用 Python iterables，但是如果我们需要一个计数器来跟踪当前 iterable 中的所有项目，该怎么办？Python 提供了一个名为 *enumerate()* 的方法，该方法向 iterable 添加一个计数器，然后以枚举对象的形式返回该计数器。它也可以用在循环构造中，在循环构造中需要对 iterable 中的每一项都有一个计数器。

想了解更多，一定要阅读:[**Python 中的枚举法**](https://www.geeksforgeeks.org/enumerate-in-python/)

### 4.Python 的收集模块

Python 有一个惊人的模块叫做*集合*，用来实现容器数据类型，即列表、dict、set、tuple 来摆脱它们的缺点。它提供了专门的数据结构:namedtuple()、UserList、UserDict、UserString、deque、Chainmap、Counter、OrderedDict 和 defaultdict。在您的代码中使用这些可以在很大程度上提高它的性能，也让 Python 开发人员的日常编程变得更加容易。

要了解更多信息，请阅读: [**Python 集合模块**](https://www.geeksforgeeks.org/python-collections-module/)

### 5.将参数传递给 sort()方法

Python 提供了一个名为 sort()的内置函数，默认情况下，该函数按升序对列表进行排序。但是它不仅仅局限于对列表进行排序，相反，我们可以将各种参数传递给这个函数，以根据我们的需要定制结果。首先，我们可以在排序方法中传递 *reverse=True* ，这样我们就可以按降序接收列表。其次，我们可以将一个值传递给*键*，这是一个函数，用作排序比较的键。例如，如果我们有一个字符串列表，我们想根据它们的高度对它们进行排序，我们将遵循以下语法: *list_input.sort(key=len)* 。

要了解更多信息，请阅读:Python 中的[**sort()**](https://www.geeksforgeeks.org/sort-in-python/)

### 6.调试带断点的代码()

我们都承认在调试 Python 代码时使用 *print()* ，并传递各种奇怪的字符串来检查打印执行到哪一行。但是，这是一种糟糕的方法，当 Python 提供了一个名为*断点()*的函数，在我们认为可能存在潜在错误的地方测试代码时，不应该使用这种方法。有一些语句用于继续执行、退出调试器、转到同一函数或被调用函数的下一行等目的。

想了解更多，必须阅读:[**Python 中的调试**](https://www.geeksforgeeks.org/debugging-python-code-using-breakpoint-and-pdb/)

### 7.了解神秘的* *夸脱

** * Python 中的 kwargs* 用于函数定义，通常用于传递一个关键字化的参数列表，该列表可以是可变长度的。双通配符表示可以传递的参数(可变长度)的关键字数量没有限制。要使用它，我们需要为我们传递的参数提供名称，它们最终可以像字典一样被检索，而不需要任何特定的顺序。

想了解更多，必须阅读:[*** * Python 中的 kwargs**](https://www.geeksforgeeks.org/args-kwargs-python/)

### 8.使用全部或任何关键词

这些是 Python 提供的最常用的 AND/OS 内置功能之一，并且肯定会在很大程度上减少您的代码。当我们需要检查任何一项是否为真时，使用关键字 *any* 。为了便于可视化，我们可以把它看作是对调用它的可迭代对象的连续或运算。鉴于， *all* 用于检查表格中的每一项是否真实。这两个都是短路操作器，一旦在*所有*中遇到假的或者在*任何*中遇到真的就停止。

要了解更多信息，请阅读:[**【Python 中的所有任意】**](https://www.geeksforgeeks.org/any-all-in-python/)

我们已经看到了作为开发人员必须知道的各种 Python 提示和技巧，这些将帮助您在 Python 编码面试中保持对候选人的优势！