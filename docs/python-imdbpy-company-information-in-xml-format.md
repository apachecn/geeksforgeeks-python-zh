# Python IMDbPY–XML 格式的公司信息

> 原文:[https://www . geesforgeks . org/python-imdbpy-company-information-in-XML-format/](https://www.geeksforgeeks.org/python-imdbpy-company-information-in-xml-format/)

在本文中，我们将看到如何获得 XML 格式的公司信息。可扩展标记语言(XML)是一种标记语言，它定义了一组规则，用于以人类可读和机器可读的格式对文档进行编码。公司对象包含与电影行业相关的公司的所有信息，并在 IMDb 数据库中有记录。

> 为了得到这一点，我们必须做以下
> 1。导入 IMDbPY 模块
> 2。创建一个 IMDB 实例
> 3。借助需要电影 ID
> 4 的 get_company 方法获取公司对象。通过将公司对象转换为 XML，在此获取 XML 格式值，它将是字符串形式

下面是实现

```
# importing the module
import imdb

# creating instance of IMDb
ia = imdb.IMDb()

# id
code = "0051941"

# getting information
company = ia.get_company(code)

# printing company
print(company) 

print("--------------------------------")

# converting company object into XML file
xml_file = company.asXML()

# printing some part of the XML file
print(xml_file[:250])
```

**输出:**

```
Marvel Studios
--------------------------------
<?xml version="1.0"?
<!DOCTYPE company SYSTEM "http://imdbpy.sf.net/dtd/imdbpy68.dtd"

<company id="0051941" access-system="http"Marvel Studios</nameMarvel Studios</long-imdb-name</compan
```

另一个例子

```
# importing the module
import imdb

# creating instance of IMDb
ia = imdb.IMDb()

# id
code = "0022125"

# getting information
company = ia.get_company(code)

# printing company
print(company) 

print("--------------------------------")

# converting company object into XML file
xml_file = company.asXML()

# printing some part of the XML file
print(xml_file[:100])
```

**输出:**

```
Pixel
--------------------------------
<?xml version="1.0"?
<!DOCTYPE company SYSTEM "http://imdbpy.sf.net/dtd/imdbpy68.dtd"

<company id
```