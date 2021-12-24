# Python IMDbPY–将系列国家作为 XML 获取

> 原文:[https://www . geesforgeks . org/python-imdbpy-get-series-country-as-XML/](https://www.geeksforgeeks.org/python-imdbpy-getting-series-countries-as-xml/)

在本文中，我们将看到如何以 XML 格式获取系列国家信息(信息集)。可扩展标记语言(XML)是一种标记语言，它定义了一组规则，用于以人类可读和机器可读的格式对文档进行编码。系列对象包含 IMDb 数据库中记录的所有剧集和季节的所有信息。有些系列有关于其来源国或发行国的信息。

> 为了得到这一点，我们必须做以下
> 1。导入 IMDbPY 模块
> 2。创建一个 IMDB 实例
> 3。借助系列 ID
> 4 获取系列对象。在此获取 XML 格式值，它将是字符串形式的，方法是借助“国家”关键字将 series 对象转换为 XML

下面是实现

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

# converting series object's COUNTRIES into XML file
xml = series.getAsXML('countries')

# printing some part of the XML file
print(xml[:100])
```

**输出:**

```
Money Heist
--------------------------------
<countries infoset="main"<item Spain</item</countries
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

# converting series object's COUNTRIES into XML file
xml = series.getAsXML('countries')

# printing some part of the XML file
print(xml[:100])
```

**输出:**

```
Sacred Games
--------------------------------
<countries infoset="main"<item India</item<item United States</item</countries
```