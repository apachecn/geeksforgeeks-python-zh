# Python IMDbPY–使用人员 ID 检索人员

> 原文:[https://www . geesforgeks . org/python-imdbpy-retrieving-person-use-person-id/](https://www.geeksforgeeks.org/python-imdbpy-retrieving-person-using-person-id/)

在本文中，我们将看到如何使用个人标识来检索个人数据，个人标识是 IMDb 给每个人的唯一标识。我们可以使用`search_person`方法按姓名搜索人员，但它会给出许多人，因为他们有相同的姓名，因此根据 id 检索人员是一个更好的选择。

为了通过一个人的身份来搜索他，我们使用`get_person`方法。

> **语法:** imdb_object.get_person(id)
> 
> **自变量:**以字符串为自变量，即为人 id
> 
> **返回:**返回 imdb Person 对象。

下面是实现。

```py
# importing the module
import imdb

# creating instance of IMDb
ia = imdb.IMDb()

# ID
code = "4731677"

# searching the Id
search = ia.get_person(code)

# printing the search
print(search)
```

**输出:**

```py
Ayushmann Khurrana
```

另一个例子

```py
# importing the module
import imdb

# creating instance of IMDb
ia = imdb.IMDb()

# ID
code = "2690647"

# searching the Id
search = ia.get_person(code)

# printing the search
print(search)
```

**输出:**

```py
Pankaj Tripathi
```