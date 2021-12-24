# Python–Tweepy 中的 API.show_list_member()

> 原文:[https://www . geesforgeks . org/python-API-show _ list _ member-in-tweepy/](https://www.geeksforgeeks.org/python-api-show_list_member-in-tweepy/)

**推特**是一个流行的社交网络，用户在这里分享被称为推文的消息。推特允许我们使用推特应用编程接口或 **Tweepy** 挖掘任何用户的数据。这些数据将是从用户那里提取的推文。首先要做的是从 twitter developer 获取消费者密钥、消费者秘密、访问密钥和访问秘密，每个用户都可以轻松获得。这些密钥将帮助应用编程接口进行身份验证。

## API.show_list_member()

Tweepy 模块中`API`类的 **`show_list_member()`** 方法用于检查指定用户是否是指定列表的成员。

> **语法:** API.show_list_member(参数)
> 
> **参数:**
> 
> *   **列表 _id :** 列表的 id。
> *   **鼻涕虫:**列表中的鼻涕虫。
> *   **用户 _id :** 列表中待检查用户的 id。
> *   **screen_name :** 列表中待检查用户的屏幕名称。
> *   **所有者 _id :** 列表所有者的 id。
> *   **所有者 _ 屏幕 _ 名称:**列表所有者的屏幕名称。
> 
> **返回:**用户类的对象

**示例 1 :** 当用户是列表的成员时。

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
list_id = 

# the user to be checked in the list
screen_name = "geeksforgeeks"

# checking the user is present in the list or not
api.show_list_member(list_id = list_id, screen_name = screen_name)

# if there is no exception then the user is present
print("The user " + screen_name + " is present in the list.")
```

**输出:**

```py
The user geeksforgeeksis present in the list.

```

**示例 2 :** 当用户不是列表的成员时。

```py
# the ID of the list
list_id = 

# the user to be checked in the list
screen_name = "abcxyz"

# checking the user is present in the list or not
api.show_list_member(list_id = list_id, screen_name = screen_name)

# if there is no exception then the user is present
print("The user " + screen_name + " is present in the list.")
```

**输出:**

```py
raise TweepError(error_msg, resp, api_code=api_error_code)
tweepy.error.TweepError: [{'code': 108, 'message': 'Cannot find specified user.'}]

```