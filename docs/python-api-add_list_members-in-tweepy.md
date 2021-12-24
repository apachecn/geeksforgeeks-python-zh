# Python–Tweepy

中的 API.add_list_members()

> 原文:[https://www . geesforgeks . org/python-API-add _ list _ members-in-tweepy/](https://www.geeksforgeeks.org/python-api-add_list_members-in-tweepy/)

**推特**是一个流行的社交网络，用户在这里分享被称为推文的消息。推特允许我们使用推特应用编程接口或 **Tweepy** 挖掘任何用户的数据。这些数据将是从用户那里提取的推文。首先要做的是从 twitter developer 获取消费者密钥、消费者秘密、访问密钥和访问秘密，每个用户都可以轻松获得。这些密钥将帮助应用编程接口进行身份验证。

## API.add_list_members()

Tweepy 模块中`API`类的 **`add_list_members()`** 方法用于向指定列表添加多个成员。

> **语法:** API.add_list_members(参数)
> 
> **参数:**
> 
> *   **列表 _id :** 列表的 id。
> *   **鼻涕虫:**列表中的鼻涕虫。
> *   **用户 _id :** 要添加到列表中的用户的 id。
> *   **屏幕名称:**要添加到列表中的用户的屏幕名称。
> *   **所有者 _id :** 列表所有者的 id。
> *   **所有者 _ 屏幕 _ 名称:**列表所有者的屏幕名称。
> 
> **返回:**类列表的一个对象

**示例 1 :** 使用`add_list_members()`方法向列表中添加单个成员。

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

# screen name of the user to be added
screen_name = "geeksforgeeks"

print("Number of members before add_list_member() is used : " +
      str(api.get_list(list_id = list_id).member_count))

# adding the user to the list
api.add_list_members(list_id = list_id, screen_name = screen_name)

print("Number of members after add_list_member() is used : " +
      str(api.get_list(list_id = list_id).member_count))
```

**输出:**

```py
Number of members after add_list_members() is used : 0
Number of members after add_list_members() is used : 1

```

**示例 2 :** 使用`add_list_members()`方法向列表中添加多个成员。

```py
# the ID of the non-existent list
list_id = 

# add the following users to the list
users = ["geeksforgeeks", "PracticeGfG",
         "GeeksQuiz", "hackerrank"]

print("Number of members before add_list_member() is used : " +
      str(api.get_list(list_id = list_id).member_count))

# adding the users to the list
api.add_list_members(list_id = list_id, screen_name = users)

print("Number of members after add_list_member() is used : " +
      str(api.get_list(list_id = list_id).member_count))
```

**输出:**

```py
Number of members before add_list_members() is used : 0
Number of members after add_list_members() is used : 4

```