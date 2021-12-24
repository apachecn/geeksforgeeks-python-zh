# Python IMdbpy–从搜索到的姓名中获取人名

> 原文:[https://www . geesforgeks . org/python-imdbpy-从搜索名称中获取人名/](https://www.geeksforgeeks.org/python-imdbpy-getting-person-name-from-searched-name/)

在本文中，我们将看到如何从搜索到的姓名列表中获取人名，我们使用 search_name 方法来查找所有相关的姓名。
search_name 方法返回列表，列表的每个元素都像字典一样工作，即可以通过给出数据的关键字来查询它们，这里的关键字将是 name。

> **语法:**name[0][' name ']
> 这里 name 是 search_name 方法返回的列表，name[0]是指列表的第一个元素。
> **返回:**返回字符串即名称。

下面是实现

## 蟒蛇 3

```
# importing the module
import imdb

# creating instance of IMDb
ia = imdb.IMDb()

# name of the person
name = "Nawazudin Siddiqui"

# searching the name of the person
search = ia.search_person(name)

# printing whole list
print(search)

# printing the name
for i in range(len(search)):
    print(search[i]['name'])
```

**输出:**

```
[Person id:1596350[http] name:_Nawazuddin Siddiqui_]
Nawazuddin Siddiqui
```

另一个例子:

## 蟒蛇 3

```
# importing the module
import imdb

# creating instance of IMDb
ia = imdb.IMDb()

# name of the person
name = "Neil Nitin mukesh"

# searching the name of the person
search = ia.search_person(name)

# printing the name
for i in range(len(search)):
    print(search[i]['name'])
```

**输出:**

```
Neil Nitin Mukesh
Nitin Mukesh
Naman Nitin Mukesh
Nitin Mukesh
```