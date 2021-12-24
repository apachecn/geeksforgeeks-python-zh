# Python–API . subscribe _ list()在 Tweepy 中

> 原文:[https://www . geesforgeks . org/python-API-subscribe _ list-in-tweepy/](https://www.geeksforgeeks.org/python-api-subscribe_list-in-tweepy/)

**推特**是一个流行的社交网络，用户在这里分享被称为推文的消息。推特允许我们使用推特应用编程接口或 **Tweepy** 挖掘任何用户的数据。这些数据将是从用户那里提取的推文。首先要做的是从 twitter developer 获取消费者密钥、消费者秘密、访问密钥和访问秘密，每个用户都可以轻松获得。这些密钥将帮助应用编程接口进行身份验证。

## API.subscribe_list()

Tweepy 模块中 API 类的 **subscribe_list()** 方法用于作为认证用户订阅指定列表。

> **语法:** API.subscribe_list(参数)
> **参数:**
> 
> *   **列表 _id :** 列表的 id。
> *   **鼻涕虫:**列表中的鼻涕虫。
> *   **所有者 _id :** 列表所有者的 id。
> *   **所有者 _ 屏幕 _ 名称:**列表所有者的屏幕名称。
> 
> **返回:**类列表的一个对象

**示例 1 :** 订阅列表。

## 蟒蛇 3

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

# the ID of the list
list_id =

# number of subscribers before subscribe_list() method
print("The number of subscribers before subscribe_list() method : " +
      str(api.get_list(list_id = list_id).subscriber_count))

# subscribing to the list
api.subscribe_list(list_id = list_id)

# number of subscribers after subscribe_list() method
print("The number of subscribers after subscribe_list() method : " +
      str(api.get_list(list_id = list_id).subscriber_count))
```

**输出:**

```
The number of subscribers before subscribe_list() method : 0
The number of subscribers after subscribe_list() method : 1
```

**例 2 :** 通过别人的鼻涕虫名字订阅别人的列表。

## 蟒蛇 3

```
# the ID of the list
list_id = 4343

# the slug of the list
slug = "thought-leaders"

# the screen name of the owner of the list
owner_screen_name = "kitson"

# number of subscribers before subscribe_list() method
print("The number of subscribers before subscribe_list() method : " +
      str(api.get_list(list_id = list_id).subscriber_count))

# subscribing to the list
api.subscribe_list(slug = slug, owner_screen_name = owner_screen_name)

# number of subscribers after subscribe_list() method
print("The number of subscribers after subscribe_list() method : " +
      str(api.get_list(list_id = list_id).subscriber_count))
```

**输出:**

```
The number of subscribers before subscribe_list() method : 4064
The number of subscribers after subscribe_list() method : 4065
```