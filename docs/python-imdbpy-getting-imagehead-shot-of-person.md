# Python IMDbPY–获取人物的图像(头像)

> 原文:[https://www . geesforgeks . org/python-imdbpy-get-imagehead-shot-of-person/](https://www.geeksforgeeks.org/python-imdbpy-getting-imagehead-shot-of-person/)

在本文中，我们将看到如何从人物对象中获取人物的图像/头像，imdb 人物对象的行为类似于字典，因此从人物对象中获取图像类似于从字典中获取所需信息。

> 为此，我们必须执行以下操作–
> 1。使用 get_person 方法
> 2 借助 id 获取人物对象。使用结果['头像']作为关键点获得图像链接
> 3。打印结果

**注意:**输出将是图像的链接，即字符串数据类型不是实际图像

下面是实现

## 蟒蛇 3

```py
# importing the module
import imdb

# creating instance of IMDb
ia = imdb.IMDb()

# person id
code = "1372788"

# getting person object
actor = ia.get_person(code)

# printing object it prints its name
print(actor)

# getting image
image = actor['headshot']

# printing the place
print(image)
```

**输出:**

```py
Shahid Kapoor
https://m.media-amazon.com/images/M/MV5BMjc5NTM5NjUyMV5BMl5BanBnXkFtZTgwMDEwMzU1OTE@._V1_UX67_CR0, 0, 67, 98_AL_.jpg
```

当我们打开输出链接时，会显示出来

![](img/59e02c3fd882778e53cd54692887c60a.png)

另一个例子

## 蟒蛇 3

```py
# importing the module
import imdb

# creating instance of IMDb
ia = imdb.IMDb()

# person id
code = "1596350"

# getting person object
actor = ia.get_person(code)

# printing object it prints its name
print(actor)

# getting image
image = actor['headshot']

# printing the place
print(image)
```

**输出:**

```py
Nawazuddin Siddiqui
https://m.media-amazon.com/images/M/MV5BMTU5NTQwMTI0NV5BMl5BanBnXkFtZTcwNzQyNTgxOA@@._V1_UX67_CR0, 0, 67, 98_AL_.jpg
```

当我们打开链接时，会显示

![](img/87763fd96155d8f0ba0662be438bebe1.png)