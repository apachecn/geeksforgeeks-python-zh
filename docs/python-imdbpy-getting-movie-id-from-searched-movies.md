# Python IMDbPY–从搜索到的电影中获取电影 ID

> 原文:[https://www . geesforgeks . org/python-imdbpy-get-movie-id-from-search-movies/](https://www.geeksforgeeks.org/python-imdbpy-getting-movie-id-from-searched-movies/)

在本文中，我们将看到如何从搜索到的电影中获取电影 id，电影 id 基本上是每个电影的唯一 id，因为电影名称可以相同，但 id 将是不同的。我们用`search_movie`方法搜索同名电影。

为了获得电影 id，我们使用`movieID`方法。

> **语法:**电影[0]。电影 ID
> 
> 这里的电影是 search_movie 返回的电影列表，电影[0]引用列表中的第一个元素
> 
> **论证:**不需要论证。
> 
> **返回:**返回电影标识字符串

下面是实现。

```
# importing the module
import imdb

# creating instance of IMDb
ia = imdb.IMDb()

# name 
name = "Udta punjab"

# searching the name 
search = ia.search_movie(name)

# loop for printing the name and id
for i in range(len(search)):

    # getting the id
    id = search[i].movieID

    # printing it
    print(search[i]['title'] + " : " + id )
```

**输出:**

```
Udta Punjab : 4434004
Diljit Dosanjh (Udta Punjab) : 6574338

```

另一个例子:

```
# importing the module
import imdb

# creating instance of IMDb
ia = imdb.IMDb()

# name 
name = "3 idiots"

# searching the name 
search = ia.search_movie(name)

# loop for printing the name and id
for i in range(len(search)):

    # getting the id
    id = search[i].movieID

    # printing it
    print(search[i]['title'] + " : " + id )
```

**输出:**

```
3 Idiots : 1187043
3 idiotas : 3685624
3 Idiots : 12049418
3 Idiots w/ GUNS : 0222441
3 Idiots on Wheels : 6689378
3 Idiots Try Candy! : 8474256
3 Idiots; How Cho Copes with Slump : 9419952
The Idiots : 0154421
Idiots : 0341476
Vidiots : 5830890
Idiotest : 3607166
Idiotsitter : 3532050
The Idiot : 0043614
Idioten : 7147976
Idiots : 1687235
4 Idiots : 6470848
Idiots : 2622956
The Idiot : 0051762
Idiots : 6866900
Idiot : 0366028

```