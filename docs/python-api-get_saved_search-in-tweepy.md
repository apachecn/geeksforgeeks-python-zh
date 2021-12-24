# Python–API . get _ saved _ search()在 Tweepy 中

> 原文:[https://www . geesforgeks . org/python-API-get _ saved _ search-in-tweepy/](https://www.geeksforgeeks.org/python-api-get_saved_search-in-tweepy/)

**推特**是一个流行的社交网络，用户在这里分享被称为推文的消息。推特允许我们使用推特应用编程接口或 **Tweepy** 挖掘任何用户的数据。这些数据将是从用户那里提取的推文。首先要做的是从 twitter developer 获取消费者密钥、消费者秘密、访问密钥和访问秘密，每个用户都可以轻松获得。这些密钥将帮助应用编程接口进行身份验证。

## API.get_saved_search()

Tweepy 模块中`API`类的 **`get_saved_search()`** 方法用于获取特定的已保存搜索。

> **语法:** API.get_saved_search(id)
> 
> **参数:**
> 
> *   **id :** 保存的搜索的 id。
> 
> **返回:【SavedSearch 类的对象**

**示例 1 :** 访问保存的搜索并打印其查询。

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

# ID of the saved search
id = 1269503225993900032

# fetching the saved search
saved_search = api.get_saved_search(id)

# printing the information
print("The ID of the saved search is : " + str(saved_search.id))
print("The query of this saved search is : " + saved_search.query)
```

**输出:**

```py
The ID of this saved search is : 1269503225993900032
The query of this saved search is : computer

```

**例 2 :** 打印保存的搜索时间。

```py
# ID of the saved search
id = 1269503225993900032

# fetching the saved search
saved_search = api.get_saved_search(id)

# printing the information
print("The saved search " + str(saved_search.id) +
      " was created on : " + str(saved_search.created_at))
```

**输出:**

```py
The saved search 1269503225993900032 was created on : 2020-06-07 05:35:29

```