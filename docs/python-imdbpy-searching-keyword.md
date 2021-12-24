# Python IMDbPY–搜索关键词

> 原文:[https://www . geesforgeks . org/python-imdbpy-search-keyword/](https://www.geeksforgeeks.org/python-imdbpy-searching-keyword/)

在本文中，我们将看到如何在 IMDb 数据库中搜索关键词。
**关键词:**是附在片头(电影/电视剧/电视剧集)上的一个词(或一组连词)，用来描述片头期间发生的任何值得注意的对象、概念、风格或动作。关键词的主要目的是让访问者轻松搜索和发现标题。

为了搜索关键字，我们将使用 search_keyword 方法。

> **语法:** imdb_object.search_keyword(关键字)
> **参数:**以字符串为参数，为关键字
> **返回:**返回列表。

下面是实现。

## 蟒蛇 3

```py
# importing the module
import imdb

# creating instance of IMDb
ia = imdb.IMDb()

# keyword
keyword = "Delhi"

# searching keyword
search = ia.search_keyword(keyword)

# printing the search 
print(search)
```

**输出:**

```py
['delhi', 'delhi-india', 'delhi-university', 'delhi-police', 'delhi-metro', 'delhi-gang-rape', 'new-delhi', 'old-delhi', 'flight-to-delhi', 'new-delhi-india', 'golden-temple-new-delhi', 'reference-to-new-delhi', 'india-gate-new-delhi', 'qutub-minar-delhi', 'chapel-hill', 'drexel-hill', 'institute-for-international-studies-new-delhi', 'model-home', 'model-hobby', 'model-heart', 'model-husband', 'scale-model-house', 'stadelheim-prison', 'reference-to-miguel-hidalgo', 'model-24-stielhandgranate', 'drug-cartel-hid-the-records-in-the-back-of-a-painting', 'university-of-north-carolina-at-chapel-hill', 'reference-to-michael-hinky-dink-kenna', "bazar-de-l'hotel-de-ville-paris", "reference-to-le-musee-de-l'homme-paris"]
```

## 蟒蛇 3

```py
# importing the module
import imdb

# creating instance of IMDb
ia = imdb.IMDb()

# keyword
keyword = "avengers tower"

# searching keyword
search = ia.search_keyword(keyword)

# printing the search 
print(search)
```

**输出:**

```py
['avengers-tower']
```