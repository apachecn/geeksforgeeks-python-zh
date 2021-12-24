# Python–Tweepy

中的 API.show_list_subscriber()

> 原文:[https://www . geesforgeks . org/python-API-show _ list _ subscriber-in-tweepy/](https://www.geeksforgeeks.org/python-api-show_list_subscriber-in-tweepy/)

**推特**是一个流行的社交网络，用户在这里分享被称为推文的消息。推特允许我们使用推特应用编程接口或 **Tweepy** 挖掘任何用户的数据。这些数据将是从用户那里提取的推文。首先要做的是从 twitter developer 获取消费者密钥、消费者秘密、访问密钥和访问秘密，每个用户都可以轻松获得。这些密钥将帮助应用编程接口进行身份验证。

## API.show_list_subscriber()

Tweepy 模块中`API`类的 **`show_list_subscriber()`** 方法用于检查用户是否是指定列表的订阅者。

> **语法:** API.show_list_subscriber(参数)
> 
> **参数:**
> 
> *   **列表 _id :** 列表的 id。
> *   **鼻涕虫:**列表中的鼻涕虫。
> *   **屏幕名称:**被检查用户的屏幕名称。
> *   **用户 _id :** 被检查用户的用户 id。
> *   **所有者 _id :** 列表所有者的 id。
> *   **所有者 _ 屏幕 _ 名称:**列表所有者的屏幕名称。
> 
> **返回:**用户类的对象

**示例 1 :** 当用户已经订阅列表时。

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

# the ID of the list
list_id = 4343

# screen name of the user to be checked
screen_name = "LiptakCarl"

# checking if the user is subscribed to the list
api.show_list_subscriber(list_id = list_id, screen_name = screen_name)

# if no exception is raised then the user is subscribed to the list
print("The user " + screen_name + " is subscribed to the list " +
      api.get_list(list_id = list_id).name)
```

**输出:**

```py
The user LiptakCarl is subscribed to the list Thought Leaders

```

**示例 2 :** 当用户未订阅列表时，将引发异常。

```py
# the ID of the list
list_id = 4343

# screen name of the user to be checked
screen_name = "geeksforgeeks"

# checking if the user is subscribed to the list
api.show_list_subscriber(list_id = list_id, screen_name = screen_name)

# if no exception is raised then the user is subscribed to the list
print("The user " + screen_name + " is subscribed to the list " +
      api.get_list(list_id = list_id).name)
```

**输出:**

```py
    raise TweepError(error_msg, resp, api_code=api_error_code)
tweepy.error.TweepError: [{'code': 109, 'message': 'The specified user is not a subscriber of this list.'}]

```