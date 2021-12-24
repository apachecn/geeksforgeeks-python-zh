# Python IMdbpy–公司对象的默认信息

> 原文:[https://www . geesforgeks . org/python-imdbpy-default-info-of-company-object/](https://www.geeksforgeeks.org/python-imdbpy-default-info-of-company-object/)

在本文中，我们将看到如何实现通过`get_company`方法默认检索的信息集，借助`get_company_infoset`我们可以知道我们可以实现的公司的所有信息。但是并不是所有的信息都被提取出来，因为这是一个耗时的过程。

为了知道电影对象提取的默认信息，我们将使用`default_info`方法。

> **语法:** company.default_info
> 
> 这里电影是 imdb 公司对象
> 
> **论证:**不需要论证
> 
> **退货:**退货单

下面是实现

```py
# importing the module
import imdb

# creating instance of IMDb
ia = imdb.IMDb()

# ID
code = "0051941"

# searching the Id
company = ia.get_company(code)

# getting default info
info = company.default_info

# printing name
print(company['name'])

# printing the info
print(info)
```

**输出:**

```py
Marvel Studios
('main', )
```

另一个例子

```py
# importing the module
import imdb

# creating instance of IMDb
ia = imdb.IMDb()

# ID
code = "0022125"

# searching the Id
company = ia.get_company(code)

# getting default info
info = company.default_info

# printing name
print(company['name'])

# printing the info
print(info)
```

**输出:**

```py
Pixel
('main', )

```