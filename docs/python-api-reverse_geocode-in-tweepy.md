# Python–API . reverse _ geocode()在 Tweepy 中

> 原文:[https://www . geesforgeks . org/python-API-reverse _ geocode-in-tweepy/](https://www.geeksforgeeks.org/python-api-reverse_geocode-in-tweepy/)

**推特**是一个流行的社交网络，用户在这里分享被称为推文的消息。推特允许我们使用推特应用编程接口或 **Tweepy** 挖掘任何用户的数据。这些数据将是从用户那里提取的推文。首先要做的是从 twitter developer 获取消费者密钥、消费者秘密、访问密钥和访问秘密，每个用户都可以轻松获得。这些密钥将帮助应用编程接口进行身份验证。

## API.reverse_geocode()

Tweepy 模块中`API`类的 **`reverse_geocode()`** 方法用于获取所提供坐标的附近位置。

> **语法:** API.reverse_geocode(lat，long，精度，粒度，max_results)
> 
> **参数:**
> 
> *   **lat :** 位置的纬度。
> *   **长:**位置的经度。
> *   **精度:**指定要搜索的“区域”。
> *   **粒度:**默认假设为邻域，也可以是城市..
> *   **max_results :** 要获取的最大结果数。
> 
> **返回:**地点类的对象列表

**例 1 :**

```py
# import the module
import tweepy

# assign the values accordingly
consumer_key = ""
consumer_secret = ""
access_token = ""
access_token_secret = ""

# authorization of consumer key and consumer secret
auth = tweepy.OAuthHandler(consumer_key, consumer_secret)

# set access to user's access key and access secret 
auth.set_access_token(access_token, access_token_secret)

# calling the api 
api = tweepy.API(auth)

# the coordinates
lat = 28
long = 77

# fetching the locations
locations = api.reverse_geocode(lat, long)

print(str(len(locations)) + " location(s) is / are fetched.")
print("\nThe location(s) is / are :")
for location in locations:
    print(location.name)
```

**输出:**

```py
2 location(s) is/are fetched.

The location(s) is/are :
Haryana
India

```

**例 2 :** 给出无效坐标时引发异常。

```py
# invalid coordinates
lat = 200
long = 123

# fetching the locations
locations = api.reverse_geocode(lat, long)
```

**输出:**

```py
Traceback (most recent call last):
  File "C:\Users\user\AppData\Local\Programs\Python\Python37-32\tweepytesting.py", line 28, in 
    locations = api.reverse_geocode(lat, long)
  File "C:\Users\user\AppData\Local\Programs\Python\Python37-32\lib\site-packages\tweepy\binder.py", line 250, in _call
    return method.execute()
  File "C:\Users\user\AppData\Local\Programs\Python\Python37-32\lib\site-packages\tweepy\binder.py", line 236, in execute
    result = self.parser.parse(self, resp.text)
  File "C:\Users\user\AppData\Local\Programs\Python\Python37-32\lib\site-packages\tweepy\parsers.py", line 98, in parse
    result = model.parse_list(method.api, json)
  File "C:\Users\user\AppData\Local\Programs\Python\Python37-32\lib\site-packages\tweepy\models.py", line 481, in parse_list
    item_list = json_list['result']['places']
KeyError: 'result'

```