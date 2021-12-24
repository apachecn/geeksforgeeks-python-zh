# Python IMDbPY–XML 格式的电影信息

> 原文:[https://www . geesforgeks . org/python-imdbpy-movies-information-in-XML-format/](https://www.geeksforgeeks.org/python-imdbpy-movies-information-in-xml-format/)

在本文中，我们将看到如何以 XML 格式获取电影信息。可扩展标记语言(XML)是一种标记语言，它定义了一组规则，用于以人类可读和机器可读的格式对文档进行编码。

> 为了得到这一点，我们必须做以下
> 1。导入 IMDbPY 模块
> 2。创建一个 IMDB 实例
> 3。借助需要电影 ID
> 4 的 get_movie 方法获取电影对象。通过使用 asXML 方法将电影对象转换为 XML，在此获取 XML 格式值，它将是字符串形式

下面是实现

```
# importing the module
import imdb

# creating instance of IMDb
ia = imdb.IMDb()

# id
code = "1187043"

# getting information
movie = ia.get_movie(code)

# printing movie name
print(movie['title'])

print("--------------------------------")

# converting movie object into XML file
xml_file = movie.asXML()

# printing some part of the XML file
print(xml_file[:150])
```

**输出:**

```
3 Idiots
--------------------------------
<?xml version="1.0"?
<!DOCTYPE movie SYSTEM "http://imdbpy.sf.net/dtd/imdbpy68.dtd"

<cast infoset="main"<
```

另一个例子

```
# importing the module
import imdb

# creating instance of IMDb
ia = imdb.IMDb()

# id
code = "4434004"

# getting information
movie = ia.get_movie(code)

# printing movie name
print(movie['title'])

print("--------------------------------")

# converting movie object into XML file
xml_file = movie.asXML()

# printing some part of the XML file
print(xml_file[:150])
```

**输出:**

```
Udta Punjab
--------------------------------
<?xml version="1.0"?
<!DOCTYPE movie SYSTEM "http://imdbpy.sf.net/dtd/imdbpy68.dtd"

<cast infoset="main"<
```