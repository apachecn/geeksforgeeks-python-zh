# Python IMDbPY–搜索公司

> 原文:[https://www . geesforgeks . org/python-imdbpy-search-a-company/](https://www.geeksforgeeks.org/python-imdbpy-searching-a-company/)

在本文中，我们将看到如何在 IMDb 数据库中搜索该公司，IMDb 数据库中有许多与电影行业相关的公司，如漫威电影公司、迪士尼等。

为了搜索公司，我们将使用`search_company`方法。

> **语法:**IMDB _ object . search _ company(company _ name)
> 
> **自变量:**它以字符串为自变量。
> 
> **返回:**返回所有相似命名公司的列表。

下面是实现。

```
# importing the module
import imdb

# creating instance of IMDb
ia = imdb.IMDb()

# name of the person
company_name = "Marvel Studios"

# searchning the name of the person
search = ia.search_company(company_name)

# printing the result
for i in search:
    print(i)
```

**输出:**

```
Marvel Studios
Barvel Studios
Marvelous 1st Studio
Next Level Studios
Boss Level Studios
Caravel Studios
Land Marvel Animation Studios

```

另一个例子:

```
# importing the module
import imdb

# creating instance of IMDb
ia = imdb.IMDb()

# name of the person
company_name = "Alt Bala ji"

# searchning the name of the person
search = ia.search_company(company_name)

# printing the result
print(search)
```

**输出:**

```
[Company id:0642697[http] name:_ALTBalaji [in]_, Company id:0779280[http] name:_ALT Balaji [in]_]
```