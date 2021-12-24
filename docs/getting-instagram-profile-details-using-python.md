# 使用 Python 获取 Instagram 配置文件详细信息

> 原文:[https://www . geeksforgeeks . org/get-insta gram-profile-details-use-python/](https://www.geeksforgeeks.org/getting-instagram-profile-details-using-python/)

Instagram 是脸书旗下的一家照片和视频共享社交网络服务公司。在本文中，我们将学习如何使用网页抓取来获取 Instagram 配置文件的详细信息。Python 为网页抓取提供了强大的工具，我们将在这里使用美化程序。
**所需模块及安装:**
**请求:**
请求让你可以极其轻松地发送 HTTP/1.1 请求。没有必要手动添加查询字符串到你的网址。

```py
pip install requests
```

**美人汤:**
美人汤是一个可以轻松从网页上抓取信息的库。它位于 HTML 或 XML 解析器之上，为迭代、搜索和修改解析树提供了 Pythonic 习惯用法。

```py
pip install beautifulsoup4
```

**解释–**
对于给定的用户名，将进行数据抓取，然后进行数据解析，以便输出可读。输出将是描述，即追随者计数，后续计数，文章计数。
下面是实现–

## 蟒蛇 3

```py
# importing libraries
from bs4 import BeautifulSoup
import requests

# instagram URL
URL = "https://www.instagram.com/{}/"

# parse function
def parse_data(s):

    # creating a dictionary
    data = {}

    # splitting the content
    # then taking the first part
    s = s.split("-")[0]

    # again splitting the content
    s = s.split(" ")

    # assigning the values
    data['Followers'] = s[0]
    data['Following'] = s[2]
    data['Posts'] = s[4]

    # returning the dictionary
    return data

# scrape function
def scrape_data(username):

    # getting the request from url
    r = requests.get(URL.format(username))

    # converting the text
    s = BeautifulSoup(r.text, "html.parser")

    # finding meta info
    meta = s.find("meta", property ="og:description")

    # calling parse method
    return parse_data(meta.attrs['content'])

# main function
if __name__=="__main__":

    # user name
    username = "geeks_for_geeks"

    # calling scrape function
    data = scrape_data(username)

    # printing the info
    print(data)
```

**Output :** 

```py
{'Followers': '120.2k', 'Following': '0', 'Posts': '702'}
```