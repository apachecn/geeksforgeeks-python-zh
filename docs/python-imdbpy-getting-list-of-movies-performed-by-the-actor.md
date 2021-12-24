# Python IMDbPY–获取演员表演的电影列表

> 原文:[https://www . geesforgeks . org/python-imdbpy-get-电影列表-由演员表演/](https://www.geeksforgeeks.org/python-imdbpy-getting-list-of-movies-performed-by-the-actor/)

在本文中，我们将看到如何获得演员表演过的电影列表，即演员在各种电影中的表演。IMDb 有一个数据库，里面有几乎每一部由经过验证的演员出演的电影。

为了得到演员表演的所有电影的列表，我们必须得到演员从影记录的细节

> **语法:**results = ia . get _ person _ film graphy(ID)
> 这里`ia`是 IMDb 对象
> 
> **自变量:**它以 Id 为自变量
> 
> **返回:**返回字典
> 
> 这个方法返回复杂的难以阅读的字典，以便得到我们使用的电影的标题`results['data']['filmography'][0]['actor'][index]`

下面是实现

```py
# importing the module
import imdb

# creating instance of IMDb
ia = imdb.IMDb()

# person id
code = "1372788"

# printing person name
print(ia.get_person(code))

# getting information
actor_results = ia.get_person_filmography(code)

# printing movie name
for index in range(5):
    movie_name = actor_results['data']['filmography'][0]['actor'][index]
    print(movie_name)
```

**输出:**

```py
Shahid Kapoor
Jersey Hindi Remake
Sachet Tandon: Bekhayali
Kabir Singh
The Insider's Watchlist
Akhil Sachdeva & Tulsi Kumar: Tera Ban Jaunga
```

另一个例子

```py
# importing the module
import imdb

# creating instance of IMDb
ia = imdb.IMDb()

# person id
code = "0001098"

# printing person name
print(ia.get_person(code))

# getting information
actor_results = ia.get_person_filmography(code)

# printing movie name
for index in range(5):
    movie_name = actor_results['data']['filmography'][0]['actor'][index]
    print(movie_name)
```

**输出:**

```py
Rodney Dangerfield
Angels with Angles
Still Standing
Back by Midnight
Phil of the Future
The Electric Piper
```