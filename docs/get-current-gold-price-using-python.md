# 使用 Python 获取当前黄金价格

> 原文:[https://www . geesforgeks . org/get-current-gold-price-use-python/](https://www.geeksforgeeks.org/get-current-gold-price-using-python/)

在这篇文章中，我们将看到如何在印度获得当前的黄金价格。黄金价格随着时间的推移而变化，黄金价格是由供给、需求和投资者行为共同决定的。这看起来很简单，但这些因素共同作用的方式有时是违反直觉的。
**所需模块及安装:**
**请求:**
请求让你可以极其轻松地发送 HTTP/1.1 请求。没有必要手动添加查询字符串到你的网址。

```
pip install requests
```

**美人汤:**
美人汤是一个可以轻松从网页上抓取信息的库。它位于 HTML 或 XML 解析器之上，为迭代、搜索和修改解析树提供了 Pythonic 习惯用法。

```
pip install beautifulsoup4
```

**解释–**
我们有黄金价格的谷歌搜索网址，我们从那里刮出以印度卢比表示的黄金价格，并将其存储在一个变量中，我们进一步将其打印出来。
下面是实现。

## 蟒蛇 3

```
# importing libraries
from bs4 import BeautifulSoup as BS
import requests

# method to get the price of gold
def get_price(url):

    # getting the request from url
    data = requests.get(url)

    # converting the text
    soup = BS(data.text, 'html.parser')

    # finding metha info for the current price
    ans = soup.find("div", class_ = "BNeawe s3v9rd AP7Wnd").text

    # returning the price
    return ans

# url of the gold price
url = "https://www.google.com / search?q = gold + price"

# calling the get_price method
ans = get_price(url)

# printing the ans
print(ans)
```

**输出:**

```
10g of 24k gold (99.9%): 42, 460 INR
```