# Python–API . geo _ id()在 Tweepy 中

> 原文:[https://www.geeksforgeeks.org/python-api-geo_id-in-tweepy/](https://www.geeksforgeeks.org/python-api-geo_id-in-tweepy/)

**推特**是一个流行的社交网络，用户在这里分享被称为推文的消息。推特允许我们使用推特应用编程接口或 **Tweepy** 挖掘任何用户的数据。这些数据将是从用户那里提取的推文。首先要做的是从 twitter developer 获取消费者密钥、消费者秘密、访问密钥和访问秘密，每个用户都可以轻松获得。这些密钥将帮助应用编程接口进行身份验证。

## API.geo_id()

Tweepy 模块中`API`类的 **`geo_id()`** 方法用于通过其推特 ID 获取位置。

> **语法:** API.geo_id(id)
> 
> **参数:**
> 
> *   **id :** 位置的推特 id。
> 
> **返回:**地点类的对象列表

**例 1 :**

```
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

# Twitter ID of London
id = "457b4814b4240d87"

# fetching the location
location = api.geo_id(id)

# printing the information
print("Place Type : " + location.place_type)
print("Name : " + location.name)
print("Full Name : " + location.full_name)
print("Country : " + location.country)
```

**输出:**

```
Place Type : city
Name : London
Full Name : London, England
Country : United Kingdom

```

**例 2 :** 给出无效 id 时引发异常。

```
# invalid ID
id = "xyz"

# fetching the location
location = api.geo_id(id)
```

**输出:**

```
    raise TweepError(error_msg, resp, api_code=api_error_code)
tweepy.error.TweepError: [{'message': 'Sorry, that page does not exist', 'code': 34}]

```