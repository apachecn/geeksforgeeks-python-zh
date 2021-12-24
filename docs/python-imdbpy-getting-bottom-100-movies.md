# Python IMDbPY–获得倒数 100 部电影

> 原文:[https://www . geesforgeks . org/python-imdbpy-get-bottom-100-movies/](https://www.geeksforgeeks.org/python-imdbpy-getting-bottom-100-movies/)

在本文中，我们将看到我们如何检索 IMDb 数据库中排名倒数 100 的电影的信息，IMDb 将所有电影的分级设置为。

为了获得 IMDb 排名垫底的 100 部电影，我们将使用`get_bottom100_movies`方法。

> **语法:**IMDB _ object . get _ bottom 100 _ movies()
> 
> **论证:**不需要论证
> 
> **返回:**返回 100 个元素的列表，每个元素都是 idbm 电影对象

下面是实现

```py
# importing the module
import imdb

# creating instance of IMDb
ia = imdb.IMDb()

# getting top 250 movies
search = ia.get_bottom100_movies()

# printing only last 10 movies title
for i in range(90, 100):
    print(search[i]['title'])
```

**输出:**

```py
Swept Away
The Adventures of Pluto Nash
Ballistic: Ecks vs. Sever
Beverly Hills Chihuahua
Holmes & Watson
Exorcist II: The Heretic
The Cat in the Hat
The Hungover Games
Street Fighter
Escape Plan 2: Hades

```