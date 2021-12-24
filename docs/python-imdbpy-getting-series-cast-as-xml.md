# Python IMdbpy–将系列转换为 XML

> 原文:[https://www . geesforgeks . org/python-imdbpy-get-series-cast-as-XML/](https://www.geeksforgeeks.org/python-imdbpy-getting-series-cast-as-xml/)

在本文中，我们将看到如何获得 XML 格式的系列转换信息(信息集)。可扩展标记语言(XML)是一种标记语言，它定义了一组规则，用于以人类可读和机器可读的格式对文档进行编码。系列对象包含 IMDb 数据库中记录的所有剧集和季节的所有信息。

基本上有两种方法，一种是过滤序列对象，即包含序列信息的 IMDbPY 对象，然后将过滤后的数据转换为 XML，这种方法既冗长又复杂，第二种方法是使用关键字，下面是这样做的方法

> 为了得到这一点，我们必须做以下
> 1。导入 IMDbPY 模块
> 2。创建一个 IMDB 实例
> 3。借助系列 ID
> 4 获取系列对象。在此获取 XML 格式值，它将是字符串形式的，方法是借助“cast”关键字将 series 对象转换为 XML

下面是实现

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

# converting series object's CAST into XML file
xml_cast = series.getAsXML('cast')

# printing some part of the XML file
print(xml_cast[:100])
print(xml_cast[100:200])
```

**输出:**

```
Sacred Games
--------------------------------
<cast infoset="main"<person id="0451307"Saif Ali Khan</name<character id=""<
name Inspector Sartaj Singh</name</character<notes</notes</current-role<current-role<character
```

另一个例子

```
# importing the module
import imdb

# creating instance of IMDb
ia = imdb.IMDb()

# id 
code = "6468322"

# getting information 
series = ia.get_movie(code) 

# printing title 
print(series.data['title']) 

print("--------------------------------")

# converting series object's CAST into XML file
xml_cast = series.getAsXML('cast')

# printing some part of the XML file
print(xml_cast[:100])
```

**输出:**

```
Money Heist
--------------------------------
<cast infoset="main"<person id="2216549"<nameÚrsula Corberó</name<current-role<character<name
```