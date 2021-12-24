# Python IMDbPY–搜索一个人

> 原文:[https://www . geesforgeks . org/python-imdbpy-search-a-person/](https://www.geeksforgeeks.org/python-imdbpy-searching-a-person/)

IMDbPY 是一个 Python 包，用于检索和管理 IMDb 的数据。在本文中，我们将看到如何在 IMDb 数据库中搜索具有给定姓名的人，我们可以借助`search_person`方法来做到这一点。

> **语法:** imdb_object.search_person(姓名)
> 
> **自变量:**以字符串为自变量，是与电影行业相关的人名。
> 
> **返回:**返回列表，列表中的项目与搜索到的名称相同或相似。

下面是实现

```py
# importing the module
import imdb

# creating instance of IMDb
ia = imdb.IMDb()

# name of the person
name = "Akshay Kumar"

# searchning the name of the person
search = ia.search_person(name)

# printing the result
for i in search :
    print(i)
```

**输出:**

```py
Akshay Kumar
Akshay Kumar
Akshay Kumar
Akshay Kumar Parija
Akshay Kumar Saxena
Akshay Kumar Pradhan
Akshay Kumar
Akshay Kumar Patil
Lakshay Kumar
Akshay Kumar
Akshay Kumar
Akshay Kumar
Akshay Kumar
Akshay Kumar
Lakshay Kumar
Akshay Kumar Ahitan
Akshay Kumar Rahi
Akshay Kumar Boral
Akshaykumar Patil
Akshay Kumar Sharma

```

另一个例子是搜索一个人

```py
# importing the module
import imdb

# creating instance of IMDb
ia = imdb.IMDb()

# name of the person
name = "Neil nitin mukesh"

# searchning the name of the person
search = ia.search_person(name)

# printing the result
print(search)
```

**输出:**

> [人员 id:1778703[http]姓名:_ 尼尔·尼汀·穆科什 _，人员 id:1042471[http]姓名:_ 尼廷·穆克什(二)_，人员 id:5068738[http]姓名:_ 纳曼·尼廷·穆克什 _，人员 id:0611482[http]姓名:_ 尼廷·穆克什(一)_]