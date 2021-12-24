# Python IMDbPY–获取人的出生日期

> 原文:[https://www . geesforgeks . org/python-imdbpy-get-出生日期-人/](https://www.geeksforgeeks.org/python-imdbpy-getting-birth-date-of-person/)

在本文中我们将看到我们如何获得任何人的出生日期，我们可以通过传递个人 id 来获得借助`get_person`方法检索的个人数据。

`get_person`方法返回一个 imdb Person 对象，该对象可以作为字典使用，即可以通过给出数据的关键字来查询它们，这里的关键字将是出生日期。

> **语法:** person['出生日期']
> 这里的 person 是 get_person 方法返回的 person 对象。
> 
> **返回:**返回出生日期字符串。

下面是实现。

```py
# importing the module
import imdb

# creating instance of IMDb
ia = imdb.IMDb()

# person id
person_id = "1596350"

# getting person details
search = ia.get_person(person_id)

# printing the search 
# printing name and birth date
print(search['name'] + "  " +search['birth date'])
```

**输出:**

```py
Nawazuddin Siddiqui  1974-05-19
```

另一个例子

```py
# importing the module
import imdb

# creating instance of IMDb
ia = imdb.IMDb()

# person id
person_id = "0000206"

# getting person details
search = ia.get_person(person_id)

# printing the search 
# printing name and birth date
print(search['name'] + "  " +search['birth date'])
```

**输出:**

```py
Keanu Reeves  1964-09-02
```