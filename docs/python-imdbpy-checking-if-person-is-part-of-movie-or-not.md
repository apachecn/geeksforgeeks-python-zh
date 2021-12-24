# Python IMDbPY–检查人物是否是电影的一部分

> 原文:[https://www . geesforgeks . org/python-imdbpy-checking-person-if-part-of-movie-or-not/](https://www.geeksforgeeks.org/python-imdbpy-checking-if-person-is-part-of-movie-or-not/)

在这篇文章中，我们将看到我们如何检查某个人是否是电影的一部分，许多人工作来制作电影，有时我们不知道某个人是否在电影中，但是在`in`操作符的帮助下，我们可以检查。

> 实施步骤:
> 
> 1.借助 get_movie 方法
> 2 获取电影数据。借助 get_person 方法
> 3 获取人物数据。在操作员检查中使用人是否是电影的一部分
> 4。显示结果

下面是实现

```
# importing the module
import imdb

# creating instance of IMDb
ia = imdb.IMDb()

# ID
code = "4434004"

# getting movie
movie = ia.get_movie(code)

# person id
code2 = "1372788"

# getting person
person = ia.get_person(code2)

# printing movie object
print(movie)

# printing person object
print(person)

print("===============")

# checking if person is in the movie or not
if person in movie:
    print("Yes !!")

else:
    print("No !!")
```

**输出:**

```
Udta Punjab
Shahid Kapoor
===============
Yes!!

```

另一个例子

```
# importing the module
import imdb

# creating instance of IMDb
ia = imdb.IMDb()

# ID
code = "1187043"

# getting movie
movie = ia.get_movie(code)

# person id
code2 = "1372788"

# getting person
person = ia.get_person(code2)

# printing movie object
print(movie)

# printing person object
print(person)

print("===============")

# checking if person is in the movie or not
if person in movie:
    print("Yes !!")

else:
    print("No !!")
```

**输出:**

```
3 Idiots
Shahid Kapoor
===============
No!!

```