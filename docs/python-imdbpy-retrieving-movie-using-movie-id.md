# Python IMDbPY–使用电影 ID 检索电影

> 原文:[https://www . geesforgeks . org/python-imdbpy-retrieving-movie-using-movie-id/](https://www.geeksforgeeks.org/python-imdbpy-retrieving-movie-using-movie-id/)

在本文中，我们将看到如何使用电影 id 检索电影数据，电影 id 是 IMDb 给每部电影的唯一 ID。我们可以使用`search_movie`方法按名称搜索电影，但它会给出许多同名电影，因此按 id 检索电影是一个更好的选择。

为了通过 id 搜索电影，我们使用`get_movie`方法。

> **语法:** imdb_object.get_movie(id)
> 
> **参数:**以字符串为参数，为电影 id
> 
> **返回:**返回 imdb Movie 对象。

下面是实现。

```py
# importing the module
import imdb

# creating instance of IMDb
ia = imdb.IMDb()

# ID
code = "1187043"

# searching the Id
search = ia.get_movie(code)

# printing the search
print(search)
```

**输出:**

```py
3 Idiots
```

另一个例子

```py
# importing the module
import imdb

# creating instance of IMDb
ia = imdb.IMDb()

# ID
code = "4434004"

# searching the Id
search = ia.get_movie(code)

# printing the search
print(search)
```

**输出:**

```py
Udta Punjab
```