# Python IMDbPY–从搜索到的电影中获取标题

> 原文:[https://www . geesforgeks . org/python-imdbpy-get-title-from-search-movie/](https://www.geeksforgeeks.org/python-imdbpy-getting-title-from-searched-movie/)

在本文中，我们将了解如何从搜索到的电影列表中获取电影的标题。我们使用 search_movie 方法来查找所有相关的电影。search_movie 方法返回列表，列表中的每个元素都像字典一样工作，即可以通过给出数据的关键字来查询它们，这里的关键字将是 title。

> **语法:** movies[0]['title']
> 这里 movies 是 search_movie 方法返回的列表，movies[0]是指列表的第一个元素。
> **返回**:返回字符串即标题。

下面是实现:

## 蟒蛇 3

```py
# importing the module
import imdb

# creating instance of IMDb
ia = imdb.IMDb()

# name of the movie
name = "Jab Taare Utare Zameen Par"

# searching the name of the movie
search = ia.search_movie(name)

# printing whole list
print(search)

# printing the movies
for i in range(len(search)):
    print(search[i]['title'])
```

**输出:**

```py
[Movie id:8142208[http] title:_Jab Taare Utare Zameen Par (2017)_]
Jab Taare Utare Zameen Par
```

另一个例子

## 蟒蛇 3

```py
# importing the module
import imdb

# creating instance of IMDb
ia = imdb.IMDb()

# name of the movie
name = "Udta punjab"

# searching the name of the movie
search = ia.search_movie(name)

# printing the movies
for i in range(len(search)):
    print(search[i]['title'])
```

**输出:**

```py
Udta Punjab
Diljit Dosanjh (Udta Punjab)
```