# Python IMdbpy–人物对象的默认信息

> 原文:[https://www . geesforgeks . org/python-imdbpy-default-info-of-person-object/](https://www.geeksforgeeks.org/python-imdbpy-default-info-of-person-object/)

在本文中，我们将看到我们如何实现通过`get_person`方法默认检索的信息集，借助`get_person_infoset`我们可以知道我们可以实现的人的所有信息。但是并不是所有的信息都被提取出来，因为这是一个耗时的过程。

为了知道电影对象提取的默认信息，我们将使用`default_info`方法。

> **语法:** person.default_info
> 
> 这里的电影是 imdb 人物对象
> 
> **论证:**不需要论证
> 
> **退货:**退货单

下面是实现

```
# importing the module
import imdb

# creating instance of IMDb
ia = imdb.IMDb()

# ID
code = "2690647"

# searching the Id
person = ia.get_person(code)

# getting default info
info = person.default_info

# printing name
print(person['name'])

# printing the info
print(info)
```

**输出:**

```
Pankaj Tripathi
('main', 'filmography', 'biography')
```

另一个例子

```
# importing movie
from imdb.Person import Person

# getting default info
info = Person.default_info

# printing the info
print(info)
```

**输出:**

```
('main', 'filmography', 'biography')
```