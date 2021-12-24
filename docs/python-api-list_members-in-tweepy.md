# Python–Tweepy 中的 API.list_members()

> 原文:[https://www . geesforgeks . org/python-API-list _ members-in-tweepy/](https://www.geeksforgeeks.org/python-api-list_members-in-tweepy/)

**推特**是一个流行的社交网络，用户在这里分享被称为推文的消息。推特允许我们使用推特应用编程接口或 **Tweepy** 挖掘任何用户的数据。这些数据将是从用户那里提取的推文。首先要做的是从 twitter developer 获取消费者密钥、消费者秘密、访问密钥和访问秘密，每个用户都可以轻松获得。这些密钥将帮助应用编程接口进行身份验证。

## API.list_members()

Tweepy 模块中`API`类的 **`list_members()`** 方法用于从指定列表中获取所有成员。

> **语法:** API.list_members(参数)
> 
> **参数:**
> 
> *   **列表 _id :** 列表的 id。
> *   **鼻涕虫:**列表中的鼻涕虫。
> *   **所有者 _id :** 列表所有者的 id。
> *   **所有者 _ 屏幕 _ 名称:**列表所有者的屏幕名称。
> 
> **返回:**用户类的对象列表

**示例 1 :** 打印列表中所有成员的屏幕名称。

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

# fetching the members
members = api.list_members(list_id = list_id)

# printing the member screen names
for member in members:
    print(member.screen_name)
```

**输出:**

```py
PracticeGfG
GeeksQuiz
geeksforgeeks

```

**例 2 :** 统计列表中成员的数量。

```py
# the ID of the list
list_id = 

# fetching the members
members = api.list_members(list_id = list_id)

# printing the number of members
print(len(members))
```

**输出:**

```py
3

```