# Python IMDbPY–获得前 250 部电影

> 原文:[https://www . geesforgeks . org/python-imdbpy-get-top-250-movies/](https://www.geeksforgeeks.org/python-imdbpy-getting-top-250-movies/)

在这篇文章中，我们将看到我们如何检索 IMDb 数据库中排名前 250 的电影的信息，IMDb 将所有电影的分级设置为。

为了获得 IMDb 的前 250 部电影，我们将使用`get_top250_movies`方法。

> **语法:**IMDB _ object . get _ top 250 _ movies()
> 
> **论证:**不需要论证
> 
> **返回:**返回 250 个元素的列表，每个元素都是 idbm 电影对象

下面是实现

```
# importing the module
import imdb

# creating instance of IMDb
ia = imdb.IMDb()

# getting top 250 movies
search = ia.get_top250_movies()

# printing only first 10 movies title
for i in range(10):
    print(search[i]['title'])
```

**输出:**

```
The Shawshank Redemption
The Godfather
The Godfather: Part II
The Dark Knight
12 Angry Men
Schindler's List
The Lord of the Rings: The Return of the King
Pulp Fiction
The Good, the Bad and the Ugly
The Lord of the Rings: The Fellowship of the Ring

```