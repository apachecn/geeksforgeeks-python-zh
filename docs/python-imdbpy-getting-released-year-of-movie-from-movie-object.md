# Python IMDbPY–从电影对象

获得电影发行年份

> 原文:[https://www . geesforgeks . org/python-imdbpy-get-release-year-of-movie-object/](https://www.geeksforgeeks.org/python-imdbpy-getting-released-year-of-movie-from-movie-object/)

在这篇文章中我们将看到我们如何从电影对象中获得电影的发行年份，我们可以借助`search_movie`和`get_movie`方法来找到电影。

`search_movie`方法返回列表，列表中的每个元素都像字典一样工作`get_movie`方法返回一个像字典一样工作的电影对象，即它们可以通过给出数据的关键字来查询，这里的关键字将是年份。

> **语法:**电影['年']
> 
> 这里的电影是 imdb 电影对象
> 
> **返回:**返回整数，即发布年份

下面是实现

```
# importing the module
import imdb

# creating instance of IMDb
ia = imdb.IMDb()

# getting the movie with id
search = ia.get_movie("0111161")

# getting movie year
year = search['year']

# printing movie name and year
print(search['title'] + " : " + str(year))
```

**输出:**

```
The Shawshank Redemption : 1994
```

另一个例子

```
# importing the module
import imdb

# creating instance of IMDb
ia = imdb.IMDb()

# getting the movie with name
search = ia.search_movie("3 Idiots")

# getting movie year
year = search[0]['year']

# printing movie name and year
print(search[0]['title'] + " : " + str(year))
```

**输出:**

```
3 Idiots : 2009
```