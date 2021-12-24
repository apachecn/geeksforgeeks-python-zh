# Python–各国冠状病毒病例详情

> 原文:[https://www . geesforgeks . org/python-各国冠状病毒病例详情/](https://www.geeksforgeeks.org/python-details-of-coronavirus-cases-in-various-countries/)

在本文中，我们将看到如何制作一个脚本，仅通过键入国家的名称就可以获得冠状病毒病例的详细信息，即总病例数、恢复病例数和总死亡人数。
**所需模块及安装:**
**请求:**请求让你可以极其轻松地发送 HTTP/1.1 请求。没有必要手动添加查询字符串到你的网址。

```py
pip install requests
```

**美人汤:**美人汤是一个库，可以方便的从网页上刮取信息。它位于 HTML 或 XML 解析器之上，为迭代、搜索和修改解析树提供了 Pythonic 习惯用法。

```py
pip install beautifulsoup4
```

> **为了制作这个剧本我们要做以下几点:**
> 1。从国家名称创建网址
> 2。借助请求和靓汤
> 3 刮数据。将数据转换成 html 代码。
> 4。找到所需的详细信息并进行筛选。
> 5。将结果保存在字典中。

下面是实现–

## 蟒蛇 3

```py
# importing libraries
from bs4 import BeautifulSoup as BS
import requests

# method to get the info
def get_info(country_name):

    # creating url using country name
    url = "https://www.worldometers.info/coronavirus/country/" + country_name + "/"

    # getting the request from url
    data = requests.get(url)

    # converting the text
    soup = BS(data.text, 'html.parser')  

    # finding meta info for cases
    cases = soup.find_all("div", class_ = "maincounter-number")

    # getting total cases number
    total = cases[0].text

    # filtering it
    total = total[1 : len(total) - 2]

    # getting recovered cases number
    recovered = cases[2].text

    # filtering it
    recovered = recovered[1 : len(recovered) - 1]

    # getting death cases number
    deaths = cases[1].text

    # filtering it
    deaths = deaths[1 : len(deaths) - 1]

    # saving details in dictionary
    ans ={'Total Cases' : total, 'Recovered Cases' : recovered,
                                 'Total Deaths' : deaths}

    # returning the dictionary
    return ans

# setting country name
country_name = "us"

# calling the get_info method
us = get_info(country_name)

# printing the results for us
print("Cases in United States")
for i, j in us.items():
    print(i + " : " + j)

print("----------------------------") 
# setting country name to india
country_name = "india"

# calling the get_info method
india = get_info(country_name)

# printing the results for us
print("Cases in India")
for i, j in india.items():
    print(i + " : " + j)
```

**输出:**

```py
Cases in United States
Total Cases : 654,343
Recovered Cases : 56,618
Total Deaths : 33,490
----------------------------
Cases in India
Total Cases : 12,759
Recovered Cases : 1,514
Total Deaths : 423
```