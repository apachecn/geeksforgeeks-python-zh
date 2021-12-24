# HTML 清理和实体转换| Python

> 原文:[https://www . geesforgeks . org/html-清洗和实体转换-python/](https://www.geeksforgeeks.org/html-cleaning-and-entity-conversion-python/)

网页上最重要的也是最容易被忽视的任务就是文本的清理。每当人们想解析 HTML 时，总是避免嵌入 Javascript 和 CSS。用户只对网络服务器上的标签和文本感兴趣。

**`lxml` 安装–**
是 C 库–**libxslt**和 **libxml2** 的 Python 绑定。所以维护一个 Python 库，它是非常快速的 HTML 解析和 XML 库。为了让它工作，还需要安装 C 库。链接–**http://lxml.de/installation.html**将提供所有安装说明。

```py
sudo apt-get install python-lxml *or*
pip install lxml
```

使用`lxml.html.clean`模块中的`clean_html()`功能执行清洁任务。这个函数删除不必要的 HTML 标签。在下面的代码中， `lxml.html.clean`模块中的`clean_html()`函数用于从一个 HTML 字符串中移除不必要的 HTML 标签和嵌入的 JavaScript。

**Code – Cleaning of the text**

```py
import lxml.html.clean
lxml.html.clean.clean_html('<html><head></head>
                           <bodyonload = loadfunc()>my text</body></html>')
```

**输出:**

```py
'<div><body>my text</body></div>'

```

正如你所看到的，结果更加简单和干净。因此，我们的工作很容易处理 HTML。

`**lxml.html.clean_html()**`函数在将 HTML 字符串解析成树时迭代字符串。然后，它会删除所有不太重要的节点。使用嵌入式 JavaScript，该函数还使用正则表达式替换和匹配来清除不必要属性的节点，如嵌入式 JavaScript。这个函数定义了一个默认的 Cleaner 类，使用 clean_html()方法调用。通过创建自身实例，可以定制类行为。

## 转换 HTML 实体–

诸如“`&`”或“`<`”等字符串都是 HTML 实体。这些都是普通的 ASCII 字符编码，在 HTML 中有特殊的用途。“`<`”是“`<"`的实体，因为`"<"`存在于 HTML 标签中，并且是 HTML 标签的开始字符。所以，为了逃避它 `"<"` 实体被定义了。 `"&"`是`"&"`的实体编码。
要处理 HTML 文档中的文本，请将这些实体转换回其正常字符，以便识别它们并适当使用它们。

**要求:**
1)安装美化组
2) sudo easy_install 美化组 4 或 sudo pip install 美化组 4

它是一个用于实体转换的 HTML 解析器库。它只是给定一个包含 HTML 实体的字符串，创建一个美丽组的实例。然后它检索字符串属性:

**代码–**

```py
# importing BeautifulSoup
from bs4 import BeautifulSoup

print (BeautifulSoup('<').string)

print (BeautifulSoup('&').string)
```

**输出:**

```py
'<'
'&'

```

但是反过来是不可能的，也就是说，对于美化组中的'htmlentitydefs.name2codepoint 字典中的对应值来替换它们。