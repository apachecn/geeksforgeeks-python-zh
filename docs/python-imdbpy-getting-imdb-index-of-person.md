# Python IMDbPY–获取人的 IMDb 指数

> 原文:[https://www . geesforgeks . org/python-imdbpy-get-IMDB-人物索引/](https://www.geeksforgeeks.org/python-imdbpy-getting-imdb-index-of-person/)

在本文中，我们将看到如何从 imdb 数据库中获取人员索引，imdb 给了人员索引来对他们进行分类索引不是数值它是罗马数字例如萨尔曼·可汗，SRK 有(I)作为索引，也有一些人没有索引。下图显示了人的指数是怎样的

![](img/0a8dcbf15523b6f869defb427cbb46fa.png)

> 为此，我们必须执行以下操作–
> 1。使用 get _ person _ filmography 方法
> 2 借助 id 获取人物对象。使用结果['数据']['imdbIndex']作为关键字获得索引
> 3。打印结果

**注意:**输出将是图像的链接即字符串数据类型不是实际图像
下面是实现

## 蟒蛇 3

```
# importing the module
import imdb

# creating instance of IMDb
ia = imdb.IMDb()

# person id
code = "1372788"

# getting person object
actor = ia.get_person_filmography(code)

# printing object name
print(actor['data']['name'])

# getting index
index = actor['data']['imdbIndex']

# printing
print(index)
```

**输出:**

```
Shahid Kapoor
I
```

另一个例子

## 蟒蛇 3

```
# importing the module
import imdb

# creating instance of IMDb
ia = imdb.IMDb()

# person id
code = "0262635"

# getting person object
actor = ia.get_person_filmography(code)

# printing object name
print(actor['data']['name'])

# getting index
index = actor['data']['imdbIndex']

# printing
print(index)
```

**输出:**

```
Chris Evans
V
```