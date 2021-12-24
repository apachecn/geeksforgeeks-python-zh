# Python IMdbpy–设置为电影对象关键点的信息

> 原文:[https://www . geesforgeks . org/python-imdbpy-info-set-to-key-of-movie-object/](https://www.geeksforgeeks.org/python-imdbpy-info-set-to-keys-of-movie-object/)

在本文中，我们将看到如何将信息集转换为关键点，我们可以通过`get_movie_infoset`知道电影的信息集，但是即使在获得信息集后，我们也无法像字典一样使用。

为了使用信息集作为字典关键字，我们必须使用`infoset2keys`方法。

> **语法:** movie.infoset2keys
> 
> 这里的电影是 imdb 电影对象
> 
> **执行的操作:**这将允许信息集用作字典键

下面是实现

```py
# importing the module
import imdb

# creating instance of IMDb
ia = imdb.IMDb()

# ID
code = "0094226"

# searching the Id and getting info set
movie = ia.get_movie(code, info =['taglines', 'plot'])

# making infoset to use as keys
movie.infoset2keys

# printing movie tagline
print(movie['taglines'])
```

**输出:**

> [‘芝加哥梦有那么大’，‘没人惹过艾尔·卡朋，但艾略特·奈斯惹过他’，”阿尔·卡彭。他以绝对的权力统治着芝加哥。没人能碰他。没人能阻止他。直到艾略特·奈斯和一小群人发誓要打倒他。”，‘你准备做什么？’，‘在战斗结束前不要停止战斗’

另一个例子

```py
# importing the module
import imdb

# creating instance of IMDb
ia = imdb.IMDb()

# ID
code = "4434004"

# searching the Id and getting info set
movie = ia.get_movie(code, info =['plot'])

# making infoset to use as keys
movie.infoset2keys

# printing movie plot
print(movie['plot'])
```

**输出:**

> [“一个围绕富裕的印度北部旁遮普邦的药物滥用以及那里的年轻人如何集体屈服于药物滥用导致社会经济衰退的故事。”，“一个摇滚明星，一个农民工，一个医生，一个警察，到底有什么共同点？简单，旁遮普！4 条生命，1 个联系——“乌达旁遮普”带你进行一次前所未有的旅行。沙希德·卡普、卡琳娜·卡普尔、阿莉雅·布哈特和迪尔吉特·多桑赫扮演来自各行各业的角色，以他们自己的方式与毒品的威胁作斗争。这部电影在充满致命危险的道路上行走时，陷入了人为的高潮和真实的低谷。但最重要的是，乌达·旁遮普邦是著名的旁遮普精神，尽管完全消沉，但仍大胆地看着你的眼睛说——毒品，毒品！”]