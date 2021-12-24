# Python IMDbPY–XML 格式的人员信息

> 原文:[https://www . geesforgeks . org/python-imdbpy-person-information-in-XML-format/](https://www.geeksforgeeks.org/python-imdbpy-person-information-in-xml-format/)

在本文中，我们将看到如何以 XML 格式获取人员信息。可扩展标记语言(XML)是一种标记语言，它定义了一组规则，用于以人类可读和机器可读的格式对文档进行编码。Person 对象包含所有与电影行业相关的人的信息，并且在 IMDb 数据库中有记录。

> 为了得到这一点，我们必须做以下
> 1。导入 IMDbPY 模块
> 2。创建一个 IMDB 实例
> 3。借助需要电影 ID
> 4 的 get_person 方法获取人物对象。通过将 person 对象转换为 XML，在这里获取 XML 格式值，它将是字符串形式的

下面是实现

```
# importing the module
import imdb

# creating instance of IMDb
ia = imdb.IMDb()

# id
code = "1372788"

# getting information
person = ia.get_person(code)

# printing  name
print(person['name']) 

print("--------------------------------")

# converting person object into XML file
xml_file = person.asXML()

# printing some part of the XML file
print(xml_file[:150])
```

**输出:**

```
Shahid Kapoor
--------------------------------
<?xml version="1.0"?
<!DOCTYPE person SYSTEM "http://imdbpy.sf.net/dtd/imdbpy68.dtd"

<birth-info key="bir
```

另一个例子

```
# importing the module
import imdb

# creating instance of IMDb
ia = imdb.IMDb()

# id
code = "2690647"

# getting information
person = ia.get_person(code)

# printing  name
print(person['name']) 

print("--------------------------------")

# converting person object into XML file
xml_file = person.asXML()

# printing some part of the XML file
print(xml_file[:250])
```

**输出:**

```
Pankaj Tripathi
--------------------------------
<?xml version="1.0"?
<!DOCTYPE person SYSTEM "http://imdbpy.sf.net/dtd/imdbpy68.dtd"

https://m.media-amazon.com/images/M/MV5BNjdlYjllOGMtYzU1OC00ODZjLWEzOGEtMGViOTYyYjU3YmJiXk
```