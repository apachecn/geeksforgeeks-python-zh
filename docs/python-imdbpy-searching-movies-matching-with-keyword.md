# Python IMDbPY–搜索与关键词

匹配的电影

> 原文:[https://www . geesforgeks . org/python-imdbpy-search-movies-matching-with-keyword/](https://www.geeksforgeeks.org/python-imdbpy-searching-movies-matching-with-keyword/)

在这篇文章中，我们将看到如何找到具有相似关键词的电影。关键字是附加在标题(电影/电视剧/电视集)上的一个词(或一组连接的词)，用来描述标题期间发生的任何值得注意的对象、概念、风格或动作。关键词的主要目的是让访问者轻松搜索和发现标题。
为了得到关键词相似的电影，我们使用 get_keyword 方法。

> **语法:** imdb_object.get_keyword(关键字)
> **参数:**以字符串为参数即关键字
> **返回:**返回电影对象列表

下面是实现。

## 蟒蛇 3

```
# importing the module
import imdb

# creating instance of IMDb
ia = imdb.IMDb()

# keyword
keyword = "marvel"

# searching keyword
search = ia.get_keyword(keyword)

# printing the search
print(len(search))
print(search[0])
```

**输出:**

```
50
Thor: Love and Thunder
```

另一个例子

## 蟒蛇 3

```
# importing the module
import imdb

# creating instance of IMDb
ia = imdb.IMDb()

# keyword
keyword = "heaven"

# searching keyword
search = ia.get_keyword(keyword)

# printing the search
print(len(search))
print(search[0])
```

**输出:**

```
50
The Good Place (2016–2020))
```