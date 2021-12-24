# 用 Python 中的 DOM APIs 解析 XML

> 原文:[https://www . geesforgeks . org/parsing-XML-with-DOM-API-in-python/](https://www.geeksforgeeks.org/parsing-xml-with-dom-apis-in-python/)

[文档对象模型](https://www.geeksforgeeks.org/dom-document-object-model/) (DOM)是一个用于 **HTML** 和 **XML** (可扩展标记语言)文档的**编程接口**。它定义了文档的**逻辑结构**以及访问和操作文档的方式。

用 python 中的 DOM APIs 解析 XML 非常简单。出于示例的目的，我们将创建一个示例 XML 文档(sample.xml)，如下所示:

```
<?xml version="1.0"?>
<company>
    <name>GeeksForGeeks Company</name>
    <staff id="1">
        <name>Amar Pandey</name>
        <salary>8.5 LPA</salary>
    </staff>
    <staff id="2">
        <name>Akbhar Khan</name>
        <salary>6.5 LPA</salary>
    </staff>
    <staff id="3">
        <name>Anthony Walter</name>
        <salary>3.2 LPA</salary>
    </staff>
</company>
```

现在，让我们使用 python 解析上面的 XML。下面的代码演示了这个过程，

```
from xml.dom import minidom

doc = minidom.parse("sample.xml")

# doc.getElementsByTagName returns the NodeList
name = doc.getElementsByTagName("name")[0]
print(name.firstChild.data)

staffs = doc.getElementsByTagName("staff")
for staff in staffs:
        staff_id = staff.getAttribute("id")
        name = staff.getElementsByTagName("name")[0]
        salary = staff.getElementsByTagName("salary")[0]
        print("id:% s, name:% s, salary:% s" %
              (staff_id, name.firstChild.data, salary.firstChild.data))
```

**输出:**

```
GeeksForGeeks Company
id:1, name: Amar Pandey, salary:8.5 LPA
id:2, name: Akbar Khan, salary:6.5 LPA
id:3, name: Anthony Walter, salary:3.2 LPA
```

也可以使用用户定义的函数来完成相同的操作，如下面的代码所示:

```
from xml.dom import minidom

doc = minidom.parse("sample.xml")

# user-defined function
def getNodeText(node):

    nodelist = node.childNodes
    result = []
    for node in nodelist:
        if node.nodeType == node.TEXT_NODE:
            result.append(node.data)
    return ''.join(result)

name = doc.getElementsByTagName("name")[0]
print("Company Name : % s \n" % getNodeText(name))

staffs = doc.getElementsByTagName("staff")
for staff in staffs:
        staff_id = staff.getAttribute("id")
        name = staff.getElementsByTagName("name")[0]
        salary = staff.getElementsByTagName("salary")[0]
        print("id:% s, name:% s, salary:% s" %
              (staff_id, getNodeText(name), getNodeText(salary)))
```

**输出:**

```
Company Name : GeeksForGeeks Company 

id:1, name:Amar Pandey, salary:8.5 LPA
id:2, name:Akbhar Khan, salary:6.5 LPA
id:3, name:Anthony Walter, salary:3.2 LPA
```