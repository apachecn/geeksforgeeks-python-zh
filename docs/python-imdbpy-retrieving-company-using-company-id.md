# Python IMDbPY–使用公司 ID 检索公司

> 原文:[https://www . geesforgeks . org/python-imdbpy-retrieving-company-use-company-id/](https://www.geeksforgeeks.org/python-imdbpy-retrieving-company-using-company-id/)

在本文中，我们将看到如何使用公司 id 检索公司的数据，公司 id 是 IMDb 给每个公司的唯一 ID。我们可以使用`search_company`方法按名称搜索公司，但是它给出了许多公司，因为它们有相同的名称，因此根据 id 检索公司是一个更好的选择。

为了通过 id 搜索公司，我们使用`get_company`方法。

> **语法:** imdb_object.get_company(id)
> 
> **参数:**以字符串为参数，为公司 id
> 
> **返回:**返回 imdb 公司对象。

下面是实现。

```py
# importing the module
import imdb

# creating instance of IMDb
ia = imdb.IMDb()

# ID
code = "0051941"

# searching the Id
search = ia.get_company(code)

# printing the search
print(search)
```

**输出:**

```py
Marvel Studios
```

另一个例子:

```py
# importing the module
import imdb

# creating instance of IMDb
ia = imdb.IMDb()

# ID
code = "0022125"

# searching the Id
search = ia.get_company(code)

# printing the search
print(search)
```

**输出:**

```py
Pixel
```