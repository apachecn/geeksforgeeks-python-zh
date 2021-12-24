# Python IMDbPY–从电影对象中检索艺术系演员表

> 原文:[https://www . geesforgeks . org/python-imdbpy-retrieving-art-department-cast-from-the-movie-object/](https://www.geeksforgeeks.org/python-imdbpy-retrieving-art-department-cast-from-the-movie-object/)

在本文中，我们将了解如何从电影信息中检索电影中涉及的艺术系演员，电影 id 是 IMDb 赋予每部电影的唯一 id。我们可以使用 search_movie 方法按名称搜索电影，但它会给出许多同名电影，因此按 id 检索电影是一个更好的选择。

为了通过 id 搜索电影，我们使用`get_movie`方法。

> 获取艺术部门演员表的语法:cast = movie[“艺术部门”]
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
cast = movie['art department']

# actor name from caste
actor = cast[1]

print(actor)
```

**输出:**

```py
3 Idiots
===============
Ajay Chodanker

```

另一个例子:

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
cast = movie['art department']

# printing actors name from caste
print(cast[0])
```

**输出:**

```py
Udta Punjab
===============
Pallavi Pethkar

```