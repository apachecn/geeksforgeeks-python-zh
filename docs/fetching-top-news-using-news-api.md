# 使用新闻 API 获取热门新闻

> 原文:[https://www . geesforgeks . org/taking-top-news-use-news-API/](https://www.geeksforgeeks.org/fetching-top-news-using-news-api/)

新闻应用编程接口是一个简单的基于 JSON 的 REST 应用编程接口，用于从网络上搜索和检索新闻文章。利用这个，人们可以获取新闻网站上的头条新闻，或者搜索特定主题(或关键词)的头条新闻。

可以根据某些标准检索新闻。假设要搜索的主题(关键词)是“极客”(极客)或可能与特定渠道有关。一切都可以完成，但是需要 API 键才能开始。

```
Steps :

1\. Visit https://newsapi.org/ to get your own API key.

2\. Install *requests* package.
```

下面是上述想法的实现:

## 蟒蛇 3

```
# importing requests package
import requests    

def NewsFromBBC():

    # BBC news api
    # following query parameters are used
    # source, sortBy and apiKey
    query_params = {
      "source": "bbc-news",
      "sortBy": "top",
      "apiKey": "4dbc17e007ab436fb66416009dfb59a8"
    }
    main_url = " https://newsapi.org/v1/articles"

    # fetching data in json format
    res = requests.get(main_url, params=query_params)
    open_bbc_page = res.json()

    # getting all articles in a string article
    article = open_bbc_page["articles"]

    # empty list which will
    # contain all trending news
    results = []

    for ar in article:
        results.append(ar["title"])

    for i in range(len(results)):

        # printing all trending news
        print(i + 1, results[i])

    #to read the news out loud for us
    from win32com.client import Dispatch
    speak = Dispatch("SAPI.Spvoice")
    speak.Speak(results)                

# Driver Code
if __name__ == '__main__':

    # function call
    NewsFromBBC()
```

**输出:**

```
1 Italy to lift coronavirus travel restrictions
2 White House 'Operation Warp Speed' to look for Covid jab
3 Two Americas in the nation's capital
4 Kobe Bryant helicopter crash post-mortem released
5 Little things people are doing while socially distanced
6 The last 'normal' photo on your phone
7 'They came to kill the mothers'
8 EU-UK Brexit trade talks in trouble
9 Trial starts to see if dogs can 'sniff out' virus
10 Beatles photographer Astrid Kirchherr dies aged 81
```

**注意:**输出可能会根据当时排名靠前的文章而变化。

### **方法 2:**

这种方法将像蛋糕上的樱桃一样工作，因为它将根据用户输入的类别显示新闻，从而对那些想要知道特定类别/部分中的新闻的人起到过滤作用。

首先在你的系统中安装**newapi**和 **pycountry** 如果不在，使用下面的命令进行安装:

```
~ pip install newsapi-python
~ pip install pycountry
```

## 蟒蛇 3

```
from newsapi import NewsApiClient
import pycountry

# you have to get your api key from newapi.com and then paste it below
newsapi = NewsApiClient(api_key='Your API Key')

# now we will take name of country from user as input
input_country = input("Country: ")
input_countries = [f'{input_country.strip()}']
countries = {}

# iterate over all the countries in
# the world using pycountry module
for country in pycountry.countries:

    # and store the unique code of each country
    # in the dictionary along with it's full name
    countries[country.name] = country.alpha_2

# now we will check that the entered country name is
# valid or invalid using the unique code
codes = [countries.get(country.title(), 'Unknown code')
         for country in input_countries]

# now we have to display all the categories from which user will
# decide and enter the name of that category
option = input("Which category are you interested in?\n1.Business\n2.Entertainment\n3.General\n4.Health\n5.Science\n6.Technology\n\nEnter here: ")

# now we will fetch the new according to the choice of the user
top_headlines = newsapi.get_top_headlines(

    # getting top headlines from all the news channels
    category=f'{option.lower()}', language='en', country=f'{codes[0].lower()}')

  # fetch the top news inder that category
  Headlines = top_headlines['articles']

   # now we will display the that news with a good readability for user
   if Headlines:
        for articles in Headlines:
            b = articles['title'][::-1].index("-")
            if "news" in (articles['title'][-b+1:]).lower():
                print(
                    f"{articles['title'][-b+1:]}: {articles['title'][:-b-2]}.")
            else:
                print(
                    f"{articles['title'][-b+1:]} News: {articles['title'][:-b-2]}.")
    else:
        print(
            f"Sorry no articles found for {input_country}, Something Wrong!!!")
    option = input("Do you want to search again[Yes/No]?")
    if option.lower() == 'yes':
        continue
    else:
        exit()
```

**输入:**

```
Country: India
Which category are you interested in?
1.Business
2.Entertainment
3.General
4.Health
5.Science
6.Technology

Enter here: Technology
```

**输出:**

```
Gizbot News: Garena Free Fire Redeem Codes For August 16; Get Master of Minds Weapon Loot Crate.
News18: Google Pixel 5a Will Have Biggest Battery On Any Pixel Phone Ever, Launch This Month.
Hindustan Times News: PUBG Mobile: Here’s how to get the Unhinged Mortician set on PUBG Mobile, check details of RPM2 Royale Pass.
Times of India News: New iPhones, Watch, AirPods and more: What Apple may launch in September.
GSMArena.com News: Top 10 trending phones of week 32 - GSMArena.com news.
Hindustan Times News: Study finds if 'people persons' are 'machine persons' when they interact online.
Times of India News: 2021 vs 2020: August gasps for one ‘good’ air day in Gurugram this year.
ScienceAlert News: A Simple Crystal Could Finally Give Us Large-Scale Quantum Computing, Scientists Say.
Engadget News: The Switch is the first console to sweep Japan's game sales chart in 33 years.
GSMArena.com News: Weekly poll: Samsung Galaxy Z Fold3, the new S Pen and the Galaxy Z Flip3 - GSMArena.com news.
Market Research Telecast News: How to import your WhatsApp chats to WhatsApp Plus 17.00 Heymods.
Notebookcheck.net News: Realme will finally debut its first-gen laptop later in August 2021.
NewsBytes: Redmi 10 officially teased; color options revealed.
The Siasat Daily News: Xiaomi removes anti-lost mode from Mi Mix 4.
Zee News: Good news for Motorola Razr owners! Smartphone is finally getting Android 11 update.
EssentiallySports News: Animal Crossing: New Horizons- Predictions for the Next Big Update.
Republic World News: Motorola Edge 20 price in India Leaked: Price to range between Rs 21,499 to Rs 29,999.
Eurogamer.net News: Assassinations have been temporarily removed from Halo Infinite because "people just turn them off".
EssentiallySports News: Call of Duty: Warzone- If You Can Win a Game Despite the Hackers, You Can See a Vanguard Teaser.
Techradar News: Facebook Messenger voice and video calls are getting end-to-end encryption.
Do you want to search again[Yes/No]? No
```