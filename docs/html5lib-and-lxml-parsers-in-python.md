# Python 中的 html5lib 和 lxml 解析器

> 原文:[https://www . geesforgeks . org/html 5 lib-and-lxml-python 解析器/](https://www.geeksforgeeks.org/html5lib-and-lxml-parsers-in-python/)

**Python 中的解析器:**
解析简单来说就是把一团文本分解成更小更有意义的部分。这种分解取决于特定解析器定义的某些规则和因素。这些解析器可以从逐行解析的原生字符串方法到像`html5lib`这样的库，它们可以解析一个 HTML 文档的几乎所有元素，将其分解成不同的标签和片段，这些标签和片段可以被过滤掉以用于各种用例。
我们将在本文中重点讨论的两个解析器是`html5lib`和`lxml`。因此，在深入探讨它们的优缺点之前，让我们对这两个库进行一个概述。

**html5lib:** 一个*纯 python* 库，用于解析 html。它的设计符合 WHATWG HTML 规范，所有主要的网络浏览器都是这样实现的。

**lxml:** 一个针对 C 库`libxml2`和`libxslt`的成熟 Pythonic 绑定。它的独特之处在于，它将这些库的速度和 XML 特性的完整性与本机 Python 应用编程接口的简单性相结合，该接口大多与众所周知的`ElementTree`应用编程接口兼容，但优于后者。

**重点:**
由于`html5lib`是纯 python 库，所以有外部 Python 依赖关系，而`lxml`作为某些 C 库的绑定，有外部 C 依赖关系。

### 利弊:

**html5lib** :

*   实现 HTML5 解析算法，该算法受当前浏览器的影响很大，这意味着您获得的解析文本与在浏览器上获得的相同。
*   由于它使用 HTML5 解析算法，它甚至修复了许多破损的 HTML，并添加了几个丢失的标签，以完成文本并使其看起来像一个 HTML 文档。
*   极其宽大。
*   非常慢。为什么呢？因为它有大量 Python [代码](https://github.com/html5lib/html5lib-python/tree/master/html5lib)做后盾。

lxml:

*   非常快。为什么呢？因为它得到了许多“T2”代码“T3”的支持。
*   修复了一些损坏的 HTML，但并不能像完整的 HTML 文档一样展示它。
*   相当宽大。

**与 Beautifulsoup 的区别:**
为了突出两个解析器在工作方式和树的制作方面的区别，以便修复未完全形成的文档，我们将举同一个例子，并将其馈送给两个解析器。

```py
<li></p>
```

**`html5lib` :**

```py
from bs4 import BeautifulSoup

soup_html5lib = BeautifulSoup("<li></p>", "html5lib")

print(soup_html5lib)
```

**输出:**

```py
<html><head></head><body><li><p></p></li></body></html>
```

我们发现:

*   开启和关闭`html`标签。
*   打开和关闭`head`标签(空)。
*   开启和关闭`body`标签。
*   打开`p`标签支持关闭`p`标签
*   关闭`li`标签以支持打开`li`标签。
*   汤对象的最终文本中没有移除任何标记。

**`lxml` :**

```py
from bs4 import BeautifulSoup

soup_lxml = BeautifulSoup("<li></p>", "lxml")

print(soup_lxml)
```

**输出:**

```py
<html><body><li></li></body></html>
```

我们发现:

*   开启和关闭`html`标签。
*   没有`head`标签。
*   开启和关闭`body`标签。
*   关闭`li`标签以支持打开`li`标签。
*   缺少`p`标签。

我们可以很容易地观察到这两个库在最终树的形成或接收到的文档的解析方面的差异，并发现`html5lib`提供给最终解析文本的完整性。