# Python IMdbpy–向搜索到的人员添加信息集

> 原文:[https://www . geesforgeks . org/python-imdbpy-add-info-set-to-search-persons/](https://www.geeksforgeeks.org/python-imdbpy-adding-info-set-to-the-searched-persons/)

在本文中，我们将看到如何向搜索到的人添加信息集。搜索者检索固定的数据集，没有信息集的概念。因此，个人对象的信息将比默认信息集更少。例如，如果使用搜索方法，结果中的 person 对象将没有 person get 方法中可用的许多键。

为了给搜索到的人添加信息集，我们将使用`update`方法。

> **语法:**IMDB _ object . update(person _ object，info = ['传记'])
> 
> **参数:**需要两个参数，一个是我们想要更多信息的人物对象，另一个是信息集，即按键列表
> 
> **执行的操作:**将检索信息集信息

下面是实现

```py
# importing the module
import imdb

# creating instance of IMDb
ia = imdb.IMDb()

# name
name = "Amir khan"

# searching the name
persons = ia.search_person(name)

person = persons[0]

# getting more information
ia.update(person, info = ['biography'])

# printing biography
print(person['biography'])
```

**输出:**

> ['阿米尔·可汗于 1986 年 12 月 8 日出生在英国兰开夏郡的波顿。自 2013 年 5 月 31 日起，他与法亚尔·马克杜姆结婚。*匿名']

另一个例子

```py
# importing the module
import imdb

# creating instance of IMDb
ia = imdb.IMDb()

# name
name = "Robert Downey"

# searching the name
persons = ia.search_person(name)

person = persons[0]

# getting more information
ia.update(person, info = ['other works'])

# printing other works
print(person['other works'])
```

**输出:**

> ['与斯汀一起录制了《你的每一次呼吸》，与温达·薜帕德一起录制了《机会来了》，这两部电影都是为《甜心俏佳人》配乐，'(2001 年 10 月)埃尔顿·约翰的单曲《我想要爱》的音乐视频发布，来自约翰的专辑《来自西海岸的歌》，发布于 2001 年 10 月 1 日。这段视频由马修·比奇执导，小罗伯特·唐尼是唯一一个出现在视频中的人，他对口型同步了整首歌，这似乎是一个长镜头的连续拍摄，镜头跟随唐尼在一个空荡荡的大豪宅(实际上是加州贝弗利山的格雷斯通豪宅)里一间一间地拍摄。，'(2002)斯凯奇收藏鞋类杂志广告。》(2004)2003 年，他为当时是福特汽车公司卓越汽车集团旗下部门的沃尔沃汽车制作的十二分钟特辑《V50 路线》(2004)电影《线上》的推广和有限个人亮相之旅。“，”(2004 年秋冬)在福克斯体育电视宣传活动中扮演篮球角色。福克斯录制了唐尼的声音，并实际拍摄了他的嘴，使用计算机图形将其叠加在球本身上。"，'(2004 年 11 月 23 日)发行他的第一张专辑《未来主义者》，由索尼古典音乐公司/SBMG 唱片公司(SK 92654)制作，由唐尼创作并表演的八首流行民谣和查理·卓别林创作并由唐尼在 1992 年传记电影《卓别林》(1992 年)中扮演的两首封面歌曲《微笑》以及《你的举动/给和平一个机会》混合曲组成，部分来源于《是的，我见过所有好人》这首歌的前半部分，'(1992)电视广告，“你的投票就是你的声音”，由小罗伯特·唐尼和莎拉·杰西卡·帕克执导，劳伦斯·布里奇斯执导，《摇滚投票》，'(2012 年 11 月)《使命召唤:黑色行动 2》(2012)视频游戏的电视广告''(1989 年 3 月 17 日)做客《五点直播》]