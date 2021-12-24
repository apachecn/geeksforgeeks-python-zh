# 使用 Python 实时获取比特币价格

> 原文:[https://www . geesforgeks . org/get-bit-coin-price-in-time-use-python/](https://www.geeksforgeeks.org/get-bit-coin-price-in-real-time-using-python/)

在本文中，我们将了解如何获得比特币的当前价格。
**比特币**是一种加密货币。它是一种分散的数字货币，没有中央银行或单一管理员，可以在点对点比特币网络上从一个用户发送到另一个用户，而不需要中介。
**所需模块和安装:**
**请求:**
请求允许您极其轻松地发送 HTTP/1.1 请求。没有必要手动添加查询字符串到你的网址。

```
pip install requests
```

**美人汤:**
美人汤是一个可以轻松从网页上抓取信息的库。它位于 HTML 或 XML 解析器之上，为迭代、搜索和修改解析树提供了 Pythonic 习惯用法。

```
pip install beautifulsoup4
```

**解释–**
我们有比特币价格的谷歌搜索网址，我们从那里刮取了以印度卢比表示的比特币价格，并将其存储在一个变量中，然后进一步打印出来。

## 蟒蛇 3

```
# importing libraries
from bs4 import BeautifulSoup as BS
import requests

# method to get the proce of bit coin
def get_price(url):

    # getting the request from url
    data = requests.get(url)

    # converting the text
    soup = BS(data.text, 'html.parser')

    # finding metha info for the current price
    ans = soup.find("div", class_ ="BNeawe iBp4i AP7Wnd").text

    # returning the price
    return ans

# url of the bit coin price
url = "https://www.google.com / search?q = bitcoin + price"

# calling the get_price method
ans = get_price(url)

# printing the ans
print(ans)
```

**输出:**

```
520, 106.95 Indian Rupee
```