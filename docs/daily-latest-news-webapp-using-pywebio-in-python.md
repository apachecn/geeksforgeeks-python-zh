# 使用 Python 中 PyWebio 的每日最新新闻 web app

> 原文:[https://www . geesforgeks . org/daily-latest-news-web app-using-pywebio-in-python/](https://www.geeksforgeeks.org/daily-latest-news-webapp-using-pywebio-in-python/)

在本文中，我们将使用 PyWebio 创建一个获取欢乐新闻的网络应用程序

我们都下载一个应用程序来接收每日新闻，但是作为一个 python 爱好者，我们试图通过 python 脚本来做所有这些事情。这是一个通知每日新闻的 python 脚本。在这个脚本中，我们将使用 pywebio 创建一个 web 应用程序，该应用程序根据用户输入和选择的国家名称和新闻类别，将所有顶级标题显示为弹出窗口。这里我们将从网站中提取一个 API 密钥，这样我们就可以提取最新的新闻，并在特定的时间间隔后以弹出窗口的形式循环显示它们。

## 所需模块:

*   **pycountry:** pycountry 为标准提供 ISO 数据库。

```py
pip install pycountry
```

*   **pywebio:** PyWebIO 包含在浏览器上获取用户输入输出，将浏览器变成“富文本终端”的功能，可用于构建简单的 web 应用或基于浏览器的 GUI 应用。有了这个模块，任何人都可以在没有任何 HTML 和 JS 的先验知识或开销的情况下生成一个 web 应用程序。

```py
pip install pywebio
```

*   **newsapi-python:** 使用非官方的 python 客户端库将 newsapi 集成到您的 Python 应用程序中，而无需直接进行 HTTP 请求。

```py
pip install newsapi-python
```

## 逐步实施:

**第一步:**首先从 [**获取自己的 API 密钥**](https://newsapi.org/docs/client-libraries/python) 然后导入以下模块。

## 蟒蛇 3

```py
from newsapi import NewsApiClient
import time
import pycountry
from pywebio.input import *
from pywebio.output import *
from pywebio.session import *
```

**第二步:**在一个变量中加载一个 API 键(你已经从网站中提取的)，并把国家的名称作为用户的输入。

## 蟒蛇 3

```py
# copy your api id from website
# and paste it here by replacing 'Your API Key'
newsapi = NewsApiClient(api_key='Your API Key')

# required = True ensures that input can't be empty
input_country = input("", placeholder = "Enter Country Name",
                      required = True, validate = Check)
```

**步骤 3:** 现在，该功能将检查用户给出的国家名称是否有效。它通过将所有国家的**国际标准化组织代码**存储在国家字典中来进行检查，如果输入的国家不在字典中，它将返回一条错误消息。

*   将输入国家存储在变量中。
*   创建一个字典，并存储其中的所有国家及其国际标准化组织代码。
*   现在，如果用户输入的国家/地区名称出现在字典中，则继续前进，否则将返回无效国家/地区名称的错误消息。

## 蟒蛇 3

```py
def Check(input_countries):
    input_countries = [input_countries.strip()]
    countries = {}
    for country in pycountry.countries:
        countries[country.name] = country.alpha_2
    codes = [countries.get(country.title(),
                           'NO')for country in input_countries]
    if codes[0] == "NO":
        return "Wrong Country Name: Country not found..."
    return None
```

**第四步:**这里我们得到用户的选择，并根据这个选择将数据保存在变量中，以便进一步显示。

*   使用单选功能创建一个选择框列表，以便用户可以选择他/她想要获取新闻的类别。
*   然后使用 get _ top _ health 函数并将类别传递给它，将所有最新的头条新闻存储在一个变量中。

## 蟒蛇 3

```py
# create a choice box for 
# selecting type of news one wants to see
option = radio("Which category are you interested in?",
               options = ['Business', 'Entertainment', 
                          'General', 'Health','Science', 
                          'Technology'], required=True)

# extract dictionary of top
# headlines including articles etc.
top_headlines = newsapi.get_top_headlines(category = f'
                                          {option.lower()}',
                                          language='en',
                                          country=f'
                                          {codes[0].lower()}')
Headlines = top_headlines['articles']
```

**第五步:**现在我们将在特定时间间隔后以弹出窗口的形式循环打印新闻标题及其内容(您可以在下面的代码中根据自己的选择进行设置)。

## 蟒蛇 3

```py
for articles in Headlines:
  b = articles['title'][::-1].index("-")
  if "news" in (articles['title'][-b+1:]).lower():
    popup(f"{articles['title'][-b+1:]}",
          [put_html("<h4>"f"{articles['title'][:-b-2]}.""</h4>"),
           put_buttons(['Close'], onclick=lambda _: close_popup())],
          implicit_close=True)
    time.sleep(3)
  else:
    popup(f"{articles['title'][-b+1:]} News", 
          [put_html("<h4>"f"{articles['title'][:-b-2]}.""</h4>"), 
           put_buttons(['Close'], onclick=lambda _: close_popup())],
          implicit_close=True)
    time.sleep(3)
```

**以下是完整实现:**

## 蟒蛇 3

```py
from newsapi import NewsApiClient
import time
import pycountry
from pywebio.input import *
from pywebio.output import *
from pywebio.session import *

def Check(input_countries):
    input_countries = [input_countries.strip()]

    countries = {}
    for country in pycountry.countries:
        countries[country.name] = country.alpha_2

    codes = [countries.get(country.title(), 'NO')
             for country in input_countries]
    if codes[0] == "NO":
        return "Wrong Country Name: Country not found..."
    return None

# this will display the loading gif to create an
# attractive interface.
def progress():
    put_html("<p align=""center"">\
    <img src=""https://media0.giphy.com/media/kUTME7ABmhYg5J3psM/200.webp?\
    cid=ecf05e47som5hu3l2owou9vmn20hue70j113dgls1ghb1909&rid=200.webp&ct=g""\
    width=""120px""></p>
")
    time.sleep(3)
    clear()
    logo()

# this will display the image of newspaper to create
# an attractive interface.
def logo():
    put_html("<p align=""left""><h4>\
    <img src=""https://image.flaticon.com/icons/png/128/2965/2965879.png"
             " width=""28px"">NEWS</h4></p>
")

# this will display as a pop up in starting.
toast('LATEST NEWS NOTIFIER PRESENTED BY ADITYA',
      position='center', color='#000000', duration=3,
      onclick=clear)
time.sleep(3)

# this will run the below code until all
# the news headlines are displayed successfully one by one
while 1:

    clear()
    logo()

    # paste your unique API id here
    newsapi = NewsApiClient(api_key='d680fd29ce414518ad6c0585fb00143b')

    # take name of country as an input from the user
    input_country = input("", placeholder="Enter Country Name",
                          required=True, validate=Check)
    progress()
    input_countries = [f'{input_country.strip()}']

    countries = {}

    for country in pycountry.countries:
        countries[country.name] = country.alpha_2

    codes = [countries.get(country.title(),
                           'Unknown code')for country in input_countries]

    option = radio("Which category are you interested in?",
                   options=['Business', 'Entertainment',
                            'General', 'Health', 'Science',
                            'Technology'],
                   required=True)
    progress()
    top_headlines = newsapi.get_top_headlines(category=f'{option.lower()}',
                                              language='en',
                                              country=f'{codes[0].lower()}')

    Headlines = top_headlines['articles']
    if Headlines:
        for articles in Headlines:
            b = articles['title'][::-1].index("-")
            if "news" in (articles['title'][-b+1:]).lower():
                popup(f"{articles['title'][-b+1:]}",
                      [put_html("<h4>"f"{articles['title'][:-b-2]}.""</h4>"),
                       put_buttons(['Close'],
                                   onclick=lambda _: close_popup())],
                      implicit_close=True)
                time.sleep(3)
            else:
                popup(f"{articles['title'][-b+1:]} News",
                      [put_html("<h4>"f"{articles['title'][:-b-2]}.""</h4>"),
                       put_buttons(['Close'],
                                   onclick=lambda _: close_popup())],
                      implicit_close=True)
                time.sleep(3)
    else:
        put_error(f"No articles found for {input_country},
                  Try for others...", closable=True)
        time.sleep(3)
        clear()
    clear()
    logo()
    option = radio("Do you want to search again?",
                   options=['Yes', 'No'], required=True)
    if option == 'Yes':
        continue
    else:
        toast("Thanks For Visiting!")
        exit()
```

**输出:**

<video class="wp-video-shortcode" id="video-666429-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210806000042/20210805_235308.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210806000042/20210805_235308.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210806000042/20210805_235308.mp4)</video>