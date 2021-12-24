# Python |使用 lxml 从 HTML 中提取 URL

> 原文:[https://www . geesforgeks . org/python-extract-URL-from-html-using-lxml/](https://www.geeksforgeeks.org/python-extract-url-from-html-using-lxml/)

在处理 HTML 解析时，链接提取是一项非常常见的任务。对于每一个普通的网络爬虫来说，这是最重要的功能。在现有的所有 Python 库中，`**lxml**` 是最好使用的库之一。正如本文所解释的，lxml 提供了许多帮助函数来提取链接。

**lxml 安装–**

它是 C 库–`libxslt` 和`libxml2`的 Python 绑定。所以，维护一个 Python 库，它是非常快速的 HTML 解析和 XML 库。为了让它工作，还需要安装 C 库。有关安装说明，请遵循[此链接](http://lxml.de/installation.html)。

**安装命令–**

```
sudo apt-get install python-lxml *or*
pip install lxml
```

**什么是 lxml？**
它是专门为解析 html 而设计的，因此附带了一个 HTML 模块。借助`fromstring()`功能可以轻松解析 HTML 字符串。这将返回所有链接的列表。

`iterlinks()`方法有四个元组形式的参数–

> **元素:**链接是从锚标签的这个解析节点中提取的。如果只对链接感兴趣，这个可以忽略。
> **attr :** 属性的链接从哪里来，也就是简单的‘href’
> **链接:**实际的 URL 提取自锚点标签。
> **pos :** 文档中锚点标签的锚点标签数字索引。

**Code #1 :**

```
# importing library
from lxml import html
string_document = html.fromstring('hi <a href ="/world">geeks</a>')

# actual url
link = list(string_document.iterlinks())

# Link length
print ("Length of the link : ", len(link)
```

**输出:**

```
Length of the link : 1

```

**代码#2:检索`iterlinks()`元组**

```
(element, attribute, link, pos) = link[0]

print ("attribute : ", attribute)
print ("\nlink : ", link)
print ("\nposition : ", position)
```

**输出:**

```
attribute : 'href'

link : '/world'

position : 0

```

### 工作–

元素树是在 xml 解析 HTML 时建立的。ElementTree 是具有父节点和子节点的树结构。树中的每个节点代表一个 HTML 标签，它包含标签的所有相关属性。树在创建后可以被迭代以寻找元素。这些元素可以是锚点或链接标签。虽然 lxml.html 模块只包含用于创建和迭代树的特定于 HTML 的函数，但是`**lxml.etree module**`包含核心树处理代码。

### 从文件中解析 HTML–

可以用文件名或网址来调用`parse()`函数，而不是使用`fromstring()`函数来解析一个 HTML，就像`html.parse('http://the/url')`或`html.parse('/path/to/filename')`一样。加载到网址或文件中的结果将与字符串中的结果相同，然后调用`fromstring()`。

**代码#3:元素树工作**

```
import requests
import lxml.html

# requesting url
web_response = requests.get('https://www.geeksforgeeks.org/')

# building
element_tree = lxml.html.fromstring(web_response.text)

tree_title_element = element_tree.xpath('//title')[0]

print("Tag title : ", tree_title_element.tag)
print("\nText title :", tree_title_element.text_content())
print("\nhtml title :", lxml.html.tostring(tree_title_element))
print("\ntitle tag:", tree_title_element.tag)
print("\nParent's tag title:", tree_title_element.getparent().tag)
```

**输出:**

```
Tag title :  title

Text title : GeeksforGeeks | A computer science portal for geeks

html title : b'GeeksforGeeks | A computer science portal for geeks\r\n'

title tag: title

Parent's tag title: head
```

### 使用报废请求–

**请求**是一个 Python 库，用来报废网站。它使用`get()`方法请求网络服务器的网址，并以网址作为参数，作为回报，它给出响应对象。该对象将包括请求和响应的详细信息。阅读网页内容，使用 `response.text()` 方法。该内容由 web 服务器根据请求发回。

**代码#4:请求网络服务器**

```
import requests

web_response = requests.get('https://www.geeksforgeeks.org/')
print("Response from web server : \n", web_response.text)
```

**输出:**
它会生成一个巨大的脚本，这里只增加了一个样本。

```
Response from web server : 

<!DOCTYPE html>
<!--[if IE 7]>
<html class="ie ie7" lang="en-US" prefix="og: http://ogp.me/ns#">
<![endif]-->
<<!-->
<html lang="en-US" prefix="og: http://ogp.me/ns#" >
...
...
...

```