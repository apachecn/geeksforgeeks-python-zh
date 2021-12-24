# Python–API . trends _ close()在 Tweepy 中

> 原文:[https://www . geesforgeks . org/python-API-trends _ closer-in-tweepy/](https://www.geeksforgeeks.org/python-api-trends_closest-in-tweepy/)

**推特**是一个流行的社交网络，用户在这里分享被称为推文的消息。推特允许我们使用推特应用编程接口或 **Tweepy** 挖掘任何用户的数据。这些数据将是从用户那里提取的推文。首先要做的是从 twitter developer 获取消费者密钥、消费者秘密、访问密钥和访问秘密，每个用户都可以轻松获得。这些密钥将帮助应用编程接口进行身份验证。

## API.trends _ closest()

Tweepy 模块中`API`类的 **`trends_closest()`** 方法用于获取 Twitter 具有趋势主题信息的位置。

> **语法:**API . trends _ close(lat，long)
> 
> **参数:**
> 
> *   **lat :** 位置的纬度。
> *   **长:**位置的经度。
> 
> **返回:【JSON 类的一个对象**

**示例 1 :** 对德里使用`trends_closest()`方法。

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

# coordinates of Delhi
lat = 28
long = 77

# fetching the locations
locations = api.trends_closest(lat, long)

print(str(len(locations)) + " location(s) is / are fetched.")
print("\nThe location(s) is / are :")
for location in locations:
    print(location['name'])
```

**输出:**

```py
1 location(s) is/are fetched.

The location(s) is/are :
Delhi

```

**例 2 :** 给出无效坐标时引发异常。

```py
# invalid coordinates
lat = 200
long = 114

# fetching the locations
locations = api.trends_closest(lat, long)
```

**输出:**

```py
    raise TweepError(error_msg, resp, api_code=api_error_code)
tweepy.error.TweepError: [{'code': 3, 'message': 'Invalid coordinates.'}]

```