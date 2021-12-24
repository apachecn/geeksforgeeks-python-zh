# Python IMDbPY–从搜索到的公司获取名称

> 原文:[https://www . geesforgeks . org/python-imdbpy-从搜索中获取姓名-公司/](https://www.geeksforgeeks.org/python-imdbpy-getting-name-from-searched-company/)

在本文中我们将看到如何从搜索到的公司列表中获取电影公司的名称，我们使用`search_company`方法来查找所有相关的公司。

`search_company`方法返回列表，列表的每个元素都像字典一样工作，即可以通过给出数据的键来查询它们，这里的键将是名称。

> **语法:**公司[0]['名称']
> 
> 这里的公司是 search_company 方法返回的列表，公司[0]是指列表的第一个元素。
> 
> **返回**:返回字符串即名称。

下面是实现:

```py
# importing the module
import imdb

# creating instance of IMDb
ia = imdb.IMDb()

# name of the company
name = "Universal Studios Hollywood"

# searching the name of the company
search = ia.search_company(name)

# printing the search
print(search)

# printing the name
for i in range(len(search)):
    print(search[i]['name'])
```

**输出:**

```py
[Company id:0017927[http] name:_Universal Studios Hollywood [us]_]
Universal Studios Hollywood

```

另一个例子

```py
# importing the module
import imdb

# creating instance of IMDb
ia = imdb.IMDb()

# name of the company
name = "Walt Disney"

# searching the name of the company
search = ia.search_company(name)

# printing the name
for i in range(len(search)):
    print(search[i]['name'])
```

**输出:**

```py
Walt Disney Studios Motion Pictures
Walt Disney Pictures
Walt Disney Studios Motion Pictures
Walt Disney Studios
Walt Disney Animation Studios
The Walt Disney Company
Walt Disney Company
Walt Disney Company
Walt Disney Television
Walt Disney Home Video
Walt Disney Home Video
Walt Disney Productions
Walt Disney Company Nordic
Walt Disney Company
Walt Disney Attractions
The Walt Disney Company
Walt Disney Animation U.K.
Walt Disney Motion Pictures Group
Walt Disney Company
Walt Disney International

```