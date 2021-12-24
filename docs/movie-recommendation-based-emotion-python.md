# Python 中基于情感的电影推荐

> 原文:[https://www . geesforgeks . org/movie-基于推荐-情感-python/](https://www.geeksforgeeks.org/movie-recommendation-based-emotion-python/)

**引言**电影的潜在目标之一是唤起观众的情感。IMDb 提供所有类型的所有电影。因此，可以从 IMDb 列表中抓取电影标题以推荐给用户。IMDb 没有用于获取电影和电视剧信息的应用编程接口。因此，我们必须执行刮擦。[抓取](https://www.geeksforgeeks.org/implementing-web-scraping-python-beautiful-soup/)用于从网站访问信息，通常使用 API 完成。
**安装**

安装**美观套件**和**lxm**，
打开终端并写入

```py
pip install beautifulsoup4
pip install lxml
```

刮刀是用 Python 编写的，使用 lxml 来解析网页。美化输出用于从 HTML 和 XML 文件中提取数据。

**与电影类型相关的情感**

有 8 类情绪可以有效地对文本进行分类。这些是:*“愤怒”、“期待”、“厌恶”、“恐惧”、“喜悦”、“悲伤”、“惊讶”、“信任”*。在这里，这些被作为输入，并且相应的电影将被显示用于情感。
每种情感与电影类型的对应关系如下:

悲伤-戏剧
厌恶-音乐
愤怒-家庭
期待-惊悚
恐惧-运动
享受-惊悚
信任-西部
惊喜-黑色电影

基于输入的情感，相应的类型将被选择，并且该类型的所有前 5 部电影将被推荐给用户。

```py
# Python3 code for movie
# recommendation based on
# emotion

# Import library for web
# scrapping
from bs4 import BeautifulSoup as SOUP
import re
import requests as HTTP

# Main Function for scraping
def main(emotion):

    # IMDb Url for Drama genre of
    # movie against emotion Sad
    if(emotion == "Sad"):
        urlhere = 'http://www.imdb.com/search/title?genres=drama&title_type=feature&sort=moviemeter, asc'

    # IMDb Url for Musical genre of
    # movie against emotion Disgust
    elif(emotion == "Disgust"):
        urlhere = 'http://www.imdb.com/search/title?genres=musical&title_type=feature&sort=moviemeter, asc'

    # IMDb Url for Family genre of
    # movie against emotion Anger
    elif(emotion == "Anger"):
        urlhere = 'http://www.imdb.com/search/title?genres=family&title_type=feature&sort=moviemeter, asc'

    # IMDb Url for Thriller genre of
    # movie against emotion Anticipation
    elif(emotion == "Anticipation"):
        urlhere = 'http://www.imdb.com/search/title?genres=thriller&title_type=feature&sort=moviemeter, asc'

    # IMDb Url for Sport genre of
    # movie against emotion Fear
    elif(emotion == "Fear"):
        urlhere = 'http://www.imdb.com/search/title?genres=sport&title_type=feature&sort=moviemeter, asc'

    # IMDb Url for Thriller genre of
    # movie against emotion Enjoyment
    elif(emotion == "Enjoyment"):
        urlhere = 'http://www.imdb.com/search/title?genres=thriller&title_type=feature&sort=moviemeter, asc'

    # IMDb Url for Western genre of
    # movie against emotion Trust
    elif(emotion == "Trust"):
        urlhere = 'http://www.imdb.com/search/title?genres=western&title_type=feature&sort=moviemeter, asc'

    # IMDb Url for Film_noir genre of
    # movie against emotion Surprise
    elif(emotion == "Surprise"):
        urlhere = 'http://www.imdb.com/search/title?genres=film_noir&title_type=feature&sort=moviemeter, asc'

    # HTTP request to get the data of
    # the whole page
    response = HTTP.get(urlhere)
    data = response.text

    # Parsing the data using
    # BeautifulSoup
    soup = SOUP(data, "lxml")

    # Extract movie titles from the
    # data using regex
    title = soup.find_all("a", attrs = {"href" : re.compile(r'\/title\/tt+\d*\/')})
    return title

# Driver Function
if __name__ == '__main__':

    emotion = input("Enter the emotion: ")
    a = main(emotion)
    count = 0

    if(emotion == "Disgust" or emotion == "Anger"
                           or emotion=="Surprise"):

        for i in a:

            # Splitting each line of the
            # IMDb data to scrape movies
            tmp = str(i).split('>;')

            if(len(tmp) == 3):
                print(tmp[1][:-3])

            if(count > 13):
                break
            count += 1
    else:
        for i in a:
            tmp = str(i).split('>')

            if(len(tmp) == 3):
                print(tmp[1][:-3])

            if(count > 11):
                break
            count+=1
```

这个脚本将把对应于输入情感和列表的所有类型的电影标题刮给用户。

网页抓取非常有利于数据的提取和分析。没有网页抓取，你所知道的互联网就不会存在。这是因为谷歌和其他主要搜索引擎依赖一个复杂的网络抓取器来抓取将包含在它们的索引中的内容。这些工具使搜索引擎成为可能。

爬行的应用

*   精选内容的网站的文章提取。
*   为建立销售线索数据库的公司提取商业清单。
*   许多不同类型的数据提取，有时称为数据挖掘。例如，一个流行的，有时是有争议的使用网络刮刀是为了拉价格从航空公司公布在机票比较网站上。