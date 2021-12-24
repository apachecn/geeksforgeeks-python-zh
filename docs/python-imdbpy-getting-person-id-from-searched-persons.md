# Python IMDbPY–从搜索到的人员中获取人员 ID

> 原文:[https://www . geesforgeks . org/python-imdbpy-get-person-id-from-search-persons/](https://www.geeksforgeeks.org/python-imdbpy-getting-person-id-from-searched-persons/)

在这篇文章中，我们将看到如何从搜索到的人那里获得个人 id，个人 id 基本上是唯一的 id，每个人的名字可能与某些人相同，但 id 会不同。我们用`search_person`法得到同名人。

为了获得身份证，我们使用`personID`方法。

> **语法:**人[0]。拟人化
> 
> 这里的人员是 search_person 返回的人员列表，人员[0]指列表中的第一个元素
> 
> **论证:**不需要论证。
> 
> **返回:**返回字符串，即人员标识

下面是实现。

```
# importing the module
import imdb

# creating instance of IMDb
ia = imdb.IMDb()

# name 
name = "Ayushmann Khurrana"

# searching the name 
search = ia.search_person(name)

# loop for printing the name and id
for i in range(len(search)):

    # getting the id
    id = search[i].personID

    # printing it
    print(search[i]['name'] + " : " + id )
```

**输出:**

```
Ayushmann Khurrana : 4731677
```

另一个例子

```
# importing the module
import imdb

# creating instance of IMDb
ia = imdb.IMDb()

# name 
name = "Pankaj Tripathi"

# searching the name 
search = ia.search_person(name)

# loop for printing the name and id
for i in range(len(search)):

    # getting the id
    id = search[i].personID

    # printing it
    print(search[i]['name'] + " : " + id )
```

**输出:**

```
Pankaj Tripathi : 2690647
Pankaj Tripathi : 11337375
Sankalp Raj Tripathi : 9704712

```