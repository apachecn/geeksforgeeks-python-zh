# Python IMDbPY–将系列流派获取为 XML

> 原文:[https://www . geesforgeks . org/python-imdbpy-get-series-gentles-as-XML/](https://www.geeksforgeeks.org/python-imdbpy-getting-series-genres-as-xml/)

在本文中，我们将看到如何获得 XML 格式的系列风格信息(信息集)。可扩展标记语言(XML)是一种标记语言，它定义了一组规则，用于以人类可读和机器可读的格式对文档进行编码。系列对象包含 IMDb 数据库中记录的所有剧集和季节的所有信息。

体裁是任何形式或类型的交流，在任何模式下，随着时间的推移，社会认可的惯例发展。在系列中有各种类型的类型，例如喜剧，恐怖，动作等。

> 为了得到这一点，我们必须做以下
> 1。导入 IMDbPY 模块
> 2。创建一个 IMDB 实例
> 3。借助系列 ID
> 4 获取系列对象。在这里获取 XML 格式值，它将是字符串形式的，方法是借助“流派”关键字将系列对象转换为 XML

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

# converting series object's GENRES into XML file
xml = series.getAsXML('genres')

# printing some part of the XML file
print(xml[:100])
```

**输出:**

```
Money Heist
--------------------------------
<genres infoset="main"<itemAction</item<item Crime</item<item Mystery</item<itemThriller</item
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

# converting series object's GENRES into XML file
xml = series.getAsXML('genres')

# printing some part of the XML file
print(xml[:100])
```

**输出:**

```
Sacred Games
--------------------------------
<genres infoset="main"<item Action</item<item Crime</item<item Drama</item<item Thriller</item<
```