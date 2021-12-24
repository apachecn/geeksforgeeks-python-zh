# Python–API . list _ timeline()在 Tweepy 中

> 原文:[https://www . geesforgeks . org/python-API-list _ timeline-in-tweepy/](https://www.geeksforgeeks.org/python-api-list_timeline-in-tweepy/)

**推特**是一个流行的社交网络，用户在这里分享被称为推文的消息。推特允许我们使用推特应用编程接口或 **Tweepy** 挖掘任何用户的数据。这些数据将是从用户那里提取的推文。首先要做的是从 twitter developer 获取消费者密钥、消费者秘密、访问密钥和访问秘密，每个用户都可以轻松获得。这些密钥将帮助应用编程接口进行身份验证。

## API.list_timeline()

Tweepy 模块中`API`类的 **`list_timeline()`** 方法用于获取指定列表成员创作的推文的时间线。

> **语法:** API.list_timeline(参数)
> 
> **参数:**
> 
> *   **列表 _id :** 列表的 id。
> *   **鼻涕虫:**列表中的鼻涕虫。
> *   **所有者 _id :** 列表所有者的 id。
> *   **所有者 _ 屏幕 _ 名称:**列表所有者的屏幕名称。
> *   **自 _id :** 状态的 id 的最小限制。
> *   **max_id :** >状态的 id 上限。
> *   **计数:**要提取的状态数。
> *   **include_entities :** 一个包含实体节点的布尔值。
> *   **include_rts :** 包含转发的布尔值。
> 
> **返回:**类状态的对象列表

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

# the ID of the list
list_id = 

# fetching all the lists
statuses = api.list_timeline(list_id = list_id)

# counting the number of statuses fetched
print("The number of statuses fetched from the list are : " + str(len(statuses)))
```

**输出:**

```
The number of statuses fetched from the list are : 17

```

**例 2 :** 仅使用参数计数获取一定数量的状态。

```
# the ID of the list
list_id = 

# number of statuses to be fetched
count = 3

# fetching all the lists
statuses = api.list_timeline(list_id = list_id, count = count)

# counting the number of statuses fetched
print("The number of statuses fetched from the list are : " + str(len(statuses)))
```

**输出:**

```
The number of statuses fetched from the list are : 3

```