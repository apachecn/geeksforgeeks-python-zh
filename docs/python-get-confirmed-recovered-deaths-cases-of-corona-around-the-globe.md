# 巨蟒-全球范围内确认、恢复、死亡的电晕病例

> 原文:[https://www . geesforgeks . org/python-获得确认-恢复-死亡-全球电晕病例/](https://www.geeksforgeeks.org/python-get-confirmed-recovered-deaths-cases-of-corona-around-the-globe/)

在本文中，我们将看到如何创建一个 python 脚本，该脚本讲述了世界各地的电晕病例，即确诊病例数、患者康复的病例数以及电晕导致的死亡总数。
**所需模块及安装:**
**请求:**请求让你可以极其轻松地发送 HTTP/1.1 请求。没有必要手动添加查询字符串到你的网址。

```py
pip install requests
```

**美人汤:**美人汤是一个库，可以方便的从网页上刮取信息。它位于 HTML 或 XML 解析器之上，为迭代、搜索和修改解析树提供了 Pythonic 习惯用法。

```py
pip install beautifulsoup4
```

**解释–**
我们将在请求美化程序的帮助下从网站上删除数据，然后我们将原始数据转换成 html 代码，然后过滤它以获得所需的输出，并将信息保存在字典中。
下面是实现–

## 蟒蛇 3

```py
# importing libraries
from bs4 import BeautifulSoup as BS
import requests

# method to get the info
def get_info(url):

    # getting the request from url
    data = requests.get(url)

    # converting the text
    soup = BS(data.text, 'html.parser')

    # finding meta info for total cases
    total = soup.find("div", class_ = "maincounter-number").text

    # filtering it
    total = total[1 : len(total) - 2]

    # finding meta info for other numbers
    other = soup.find_all("span", class_ = "number-table")

    # getting recovered cases number
    recovered = other[2].text

    # getting death cases number
    deaths = other[3].text

    # filtering the data
    deaths = deaths[1:]

    # saving details in dictionary
    ans ={'Total Cases' : total, 'Recovered Cases' : recovered,
                                 'Total Deaths' : deaths}

    # returning the dictionary
    return ans

# url of the corona virus cases
url = "https://www.worldometers.info/coronavirus/"

# calling the get_info method
ans = get_info(url)

# printing the ans
for i, j in ans.items():
    print(i + " : " + j)
```

**输出:**

```py
Total Cases : 2,129,927
Recovered Cases : 539,063
Total Deaths : 142,716
```