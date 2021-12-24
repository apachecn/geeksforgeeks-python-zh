# Python IMDbPY–从电影细节中检索演员扮演的角色

> 原文:[https://www . geesforgeks . org/python-imdbpy-检索-电影中演员扮演的角色-详细信息/](https://www.geeksforgeeks.org/python-imdbpy-retrieving-role-played-by-actor-from-the-movie-details/)

在本文中，我们将看到如何从电影信息中检索演员在给定电影中扮演的角色，电影 id 是 IMDb 赋予每部电影的唯一 id。我们可以使用 search_movie 方法按名称搜索电影，但它会给出许多同名电影，因此按 id 检索电影是一个更好的选择。并不是强制要求所有的演员信息都会在那里，他们扮演了什么样的角色因电影而异。

为了通过 id 搜索电影，我们使用`get_movie`方法。为了获得演员名单，我们使用`movie['cast']`，其中电影是电影对象

> 获取由演员扮演的角色的语法:角色=演员[n]。笔记
> 
> 这是电影['演员阵容]返回的列表

下面是实现。

```
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
actor = cast[35]
print(actor)

# role played 
role = actor.notes

print(role)
```

**输出:**

```
3 Idiots
===============
Vaidyanathan
(as Prof. Vaidyanathan)
```

另一个例子

```
# importing the module
import imdb

# creating instance of IMDb
ia = imdb.IMDb()

# ID
code = "0075860"

# getting movie
movie = ia.get_movie(code)

# printing movie object
print(movie)

print("===============")

# getting cast
cast = movie['cast']

# actor name from caste
actor = cast[1]
print(actor)

# role played 
role = actor.notes

print(role)
```

**输出:**

```
Close Encounters of the Third Kind
===============
François Truffaut
(as Francois Truffaut)
```