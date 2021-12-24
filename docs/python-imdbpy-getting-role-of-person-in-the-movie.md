# Python IMDbPY–获得电影中人物的角色

> 原文:[https://www . geesforgeks . org/python-imdbpy-获取电影中人物角色/](https://www.geeksforgeeks.org/python-imdbpy-getting-role-of-person-in-the-movie/)

在这篇文章中，我们将看到如何在电影中得到人的角色，我们知道电影的对象行为类似于字典。IMDb 数据库有很多信息，例如电影中的工作人员的详细信息以及电影中的角色。

> 为了扮演好这个人的角色，我们必须做到以下几点–
> 1。借助 get_movie 方法
> 2 获取电影对象。从电影对象
> 3 中获取演员的详细信息。借助 currentRole 方法
> 4 获得想要的人的角色。显示结果

下面是实现

## 蟒蛇 3

```
# importing the module
import imdb

# creating instance of IMDb
ia = imdb.IMDb()

# id
code = "1187043"

# getting information
movie = ia.get_movie(code)

# printing movie name
cast = movie['cast']

# printing actor name
print(cast[0])

# getting role
role = cast[0].currentRole

# printing role
print(role)
```

**输出:**

```
Aamir Khan
Ranchoddas 'Rancho' Shyamaldas Chanchad / Phunsukh Wangdu
```

另一个例子

## 蟒蛇 3

```
# importing the module
import imdb

# creating instance of IMDb
ia = imdb.IMDb()

# id
code = "4434004"

# getting information
movie = ia.get_movie(code)

# printing movie name
cast = movie['cast']

# printing actor name
print(cast[0])

# getting role
role = cast[0].currentRole

# printing role
print(role)

```

**输出:**

```
Shahid Kapoor
Tommy Singh
```