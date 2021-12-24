# Python IMdbpy–电影对象的默认信息

> 原文:[https://www . geesforgeks . org/python-imdbpy-default-info-of-movie-object/](https://www.geeksforgeeks.org/python-imdbpy-default-info-of-movie-object/)

在本文中，我们将看到如何实现通过`get_movie`方法默认检索的信息集，借助`get_movie_infoset`我们可以知道我们可以实现的电影的所有信息。但是并不是所有的信息都被提取出来，因为这是一个耗时的过程。

为了知道电影对象提取的默认信息，我们将使用`default_info`方法。

> **语法:** movie.default_info
> 
> 这里的电影是 imdb 电影对象
> 
> **论证:**不需要论证
> 
> **退货:**退货单

下面是实现

```
# importing the module
import imdb

# creating instance of IMDb
ia = imdb.IMDb()

# ID
code = "1187043"

# searching the Id
movie = ia.get_movie(code)

# getting default info
info = movie.default_info

# printing movie title
print(movie['title'])

# printing the info
print(info)
```

**输出:**

```
3 Idiots
('main', 'plot')

```

另一个例子

```
# importing the module
import imdb

# creating instance of IMDb
ia = imdb.IMDb()

# ID
code = "4434004"

# searching the Id
movie = ia.get_movie(code)

# getting default info
info = movie.default_info

# printing movie title
print(movie['title'])

# printing the info
print(info)
```

**输出:**

```
Udta Punjab
('main', 'plot')

```