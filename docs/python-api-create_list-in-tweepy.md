# Python–API . create _ list()在 Tweepy 中

> 原文:[https://www . geesforgeks . org/python-API-create _ list-in-tweepy/](https://www.geeksforgeeks.org/python-api-create_list-in-tweepy/)

**推特**是一个流行的社交网络，用户在这里分享被称为推文的消息。推特允许我们使用推特应用编程接口或 **Tweepy** 挖掘任何用户的数据。这些数据将是从用户那里提取的推文。首先要做的是从 twitter developer 获取消费者密钥、消费者秘密、访问密钥和访问秘密，每个用户都可以轻松获得。这些密钥将帮助应用编程接口进行身份验证。

## API.create_list()

Tweepy 模块中`API`类的 **`create_list()`** 方法用于创建列表。

> **语法:** API.create_list(名称、模式、描述)
> 
> **参数:**
> 
> *   **名称:**列表名称。
> *   **url :** 列表的模式，公共或私有，默认为公共。
> *   **描述:**列表的描述。
> 
> **返回:**类列表的一个对象

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

# name of the list
name = "tweepy_list"

# creating the list
list = api.create_list(name)

print("Name of the list : " + list.name)
print("Number of members in the list : " + str(list.member_count))
print("Mode of the list : " + list.mode)
```

**输出:**

```py
Name of the list : tweepy_list
Number of members in the list : 0
Mode of the list : public

```

**例 2 :** 使用`create_list()`方法，参数模式和描述。

```py
# the name of the list
name = "tweepy_list"

# the description of the list
description = "A Tweepy list"

# the mode of the list
mode = "private"

# creating the list
list = api.create_list(name, description = description, mode = mode)

print("Name of the list : " + list.name)
print("The description of the list : " + str(list.description))
print("Mode of the list : " + list.mode)
```

**输出:**

```py
Name of the list : tweepy_list
The description of the list : A Tweepy list
Mode of the list : private

```