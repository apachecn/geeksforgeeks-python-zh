# Python IMDbPY–从搜索到的公司获取公司 ID

> 原文:[https://www . geesforgeks . org/python-imdbpy-get-company-id-from-search-companies/](https://www.geeksforgeeks.org/python-imdbpy-getting-company-id-from-searched-companies/)

在本文中，我们将看到如何从搜索到的公司获取公司 id，公司 id 基本上是每个公司的唯一 id，因为公司名称可以相同，但 id 将是不同的。我们用`search_company`方法搜索同名公司。

为了获得公司 id，我们使用`companyID`方法。

> **语法:**公司[0]。公司 ID
> 
> 这里的公司是 search_movie 返回的公司列表，公司[0]引用列表中的第一个元素。
> 
> **论证:**不需要论证。
> 
> **返回:**返回公司标识字符串

下面是实现

```
# importing the module
import imdb

# creating instance of IMDb
ia = imdb.IMDb()

# name 
name = "Marvel"

# searching the name 
search = ia.search_company(name)

# loop for printing the name and id
for i in range(len(search)):

    # getting the id
    id = search[i].companyID

    # printing it
    print(search[i]['name'] + " : " + id )
```

**输出:**

```
Marvel Studios : 0051941
Marvel Entertainment : 0047120
Marvel Family Entertainment : 0769644
Marvel Enterprises : 0095134
Marvel Productions : 0106768
Marvel Movies : 0028071
Marvelous Productions : 0644186
Marvelous : 0497759
Marvel Animation : 0249290
Marvel Comics : 0131570
Marvel Knights : 0255123
Marvel.com : 0672091
Marvel Television : 0377521
Marvelous films : 0567626
Carvell Productions : 0208235
Marvel Comics Group : 0390765
Carvel : 0039046
Marvelous Mascots : 0521917
Marvee : 0345899
Marvelous 1st Studio : 0700950
```

另一个例子

```
# importing the module
import imdb

# creating instance of IMDb
ia = imdb.IMDb()

# name 
name = "Pixel"

# searching the name 
search = ia.search_company(name)

# loop for printing the name and id
for i in range(len(search)):

    # getting the id
    id = search[i].companyID

    # printing it
    print(search[i]['name'] + " : " + id )
```

**输出:**

```
Pixel : 0022125
Pixel : 0758724
Pixel : 0445832
Pixel Magic : 0065379
Pixeldna : 0226585
Pixeleyed Pictures : 0787858
Pixelette Studios : 0335815
Pixel Brothers : 0228269
Lani Pixels : 0393856
Dilated Pixels : 0296183
PixelDog : 0436099
Pixels : 0582635
Pixell : 0405667
Big Red Pixel : 0095582
Blue Pixel : 0694611
Pixel Plus : 0395349
Zapixel : 0387827
PixelFade : 0658011
Biopixel : 0600235
Pixelpro : 0452072
?
```