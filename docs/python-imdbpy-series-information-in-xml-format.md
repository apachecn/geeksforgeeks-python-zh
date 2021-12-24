# Python IMDbPY–XML 格式的系列信息

> 原文:[https://www . geesforgeks . org/python-imdbpy-series-information-in-XML-format/](https://www.geeksforgeeks.org/python-imdbpy-series-information-in-xml-format/)

在本文中，我们将看到如何获得 XML 格式的公司信息。可扩展标记语言(XML)是一种标记语言，它定义了一组规则，用于以人类可读和机器可读的格式对文档进行编码。系列对象包含 IMDb 数据库中记录的所有剧集和季节的所有信息。

> 为了得到这一点，我们必须做以下
> 1。导入 IMDbPY 模块
> 2。创建一个 IMDB 实例
> 3。借助系列 ID
> 4 获取系列对象。通过将序列对象转换为 XML，在这里获取 XML 格式值，它将是字符串形式的

下面是实现

```
# importing the module
import imdb

# creating instance of IMDb
ia = imdb.IMDb()

# id 
code = "6473300"

# getting information 
series = ia.get_movie(code) 

# printing title 
print(series.data['title']) 

print("--------------------------------")

# converting series object into XML file
xml_file = series.asXML()

# printing some part of the XML file
print(xml_file[:100])
```

**输出:**

```
Mirzapur
--------------------------------
<?xml version="1.0"?
<!DOCTYPE movie SYSTEM "http://imdbpy.sf.net/dtd/imdbpy68.dtd"

<movie id="64
```

另一个例子

```
# importing the module
import imdb

# creating instance of IMDb
ia = imdb.IMDb()

# id 
code = "6077448"

# getting information 
series = ia.get_movie(code) 

# printing title 
print(series.data['title']) 

print("--------------------------------")

# converting series object into XML file
xml_file = series.asXML()

# printing some part of the XML file
print(xml_file[:100])
```

**输出:**

```
Sacred Games
--------------------------------
<?xml version="1.0"?
<!DOCTYPE movie SYSTEM "http://imdbpy.sf.net/dtd/imdbpy68.dtd"

<movie id="60
```