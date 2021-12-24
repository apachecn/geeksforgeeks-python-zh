# Python IMDbPY–从电影细节中检索演员

> 原文:[https://www . geesforgeks . org/python-imdbpy-检索-电影中的演员-详细信息/](https://www.geeksforgeeks.org/python-imdbpy-retrieving-actor-from-the-movie-details/)

在本文中，我们将看到如何从电影信息中检索在电影中表演的演员姓名，电影 id 是 IMDb 给每部电影的唯一 id。我们可以使用 search_movie 方法按名称搜索电影，但它会给出许多同名电影，因此按 id 检索电影是一个更好的选择。

为了通过 id 搜索电影，我们使用`get_movie`方法。

> **语法:**【获取演员名单】演员阵容=电影['演员阵容']
> 
> 这里，movie 是 get_movie 方法返回的对象，它充当字典

下面是实现。

```py
# importing the module
import imdb

# creating instance of IMDb
ia = imdb.IMDb()

# ID
code = "1187043"

# getting movie
movie = ia.get_movie(code)

# printing movie object
print(movie)

print("===============")

# getting cast
cast = movie['cast']

# actor name from caste
actor = cast[0]

# printing actor name
print(actor)
```

**输出:**

```py
3 Idiots
===============
Aamir Khan
```

另一个例子–

```py
# importing the module
import imdb

# creating instance of IMDb
ia = imdb.IMDb()

# ID
code = "4434004"

# getting movie
movie = ia.get_movie(code)

# printing movie object
print(movie)

print("===============")

# getting cast
cast = movie['cast']

# actor name from caste
actor = cast[0]

# printing actor name
print(actor)
```

**输出:**

```py
Udta Punjab
===============
Shahid Kapoor
```