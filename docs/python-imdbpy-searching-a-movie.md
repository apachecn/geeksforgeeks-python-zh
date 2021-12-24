# Python IMDbPY–搜索电影

> 原文:[https://www . geesforgeks . org/python-imdbpy-search-a-movie/](https://www.geeksforgeeks.org/python-imdbpy-searching-a-movie/)

它是一个 Python 包，用于检索和管理 IMDb 的数据。

**IMDb** 是一个与电影、电视节目、家庭视频、视频游戏和在线流媒体内容相关的在线信息数据库——包括演员、制作团队和个人传记、情节摘要、琐事、粉丝和评论以及收视率。

在本文中，我们将看到如何安装这个模块，并使用这个模块获取各种信息。

**安装**
为了从 IMDb 提取数据，首先要安装 Python IMDbP 库。这可以通过在命令提示符或终端中输入以下命令来完成:

```py
pip install IMDbPY
```

**搜索电影**T3】我们可以借助`search_movie`搜索电影

> **语法:** imdb_object.search_movie(名称)
> 
> **参数:**它以字符串作为参数，这就是电影名。
> 
> **返回:**返回列表，列表中的项目与搜索到的电影标题相同或相似。

下面是实现

```py
# importing the module
import imdb

# creating instance of IMDb
ia = imdb.IMDb()

# movie name
name = "3 idiots"

# searchning the movie
search = ia.search_movie(name)

# printing the result
for i in search:
    print(i)
```

**输出:**

```py
3 Idiots
3 idiotas
3 Idiots
3 Idiots w/ GUNS
3 Idiots on Wheels
3 Idiots Try Candy!
3 Idiots; How Cho Copes with Slump
The Idiots
Idiots
Vidiots
Idiotest
The Idiot
Idiotsitter
Idiots
Idioten
4 Idiots
Idiots
Idiots
Los 3 Idiotas
iDiots

```

另一个例子:

```py
# importing the module
import imdb

# creating instance of IMDb
ia = imdb.IMDb()

# movie name
name = "Tarzan the wonder car"

# searchning the movie
search = ia.search_movie(name)

# printing the result
print(search)
```

**输出:**

```py
[Movie id:0435437[http] title:_Taarzan: The Wonder Car (2004)_>]

```