# Python–API . create _ saved _ search()在 Tweepy 中

> 原文:[https://www . geesforgeks . org/python-API-create _ saved _ search-in-tweepy/](https://www.geeksforgeeks.org/python-api-create_saved_search-in-tweepy/)

**推特**是一个流行的社交网络，用户在这里分享被称为推文的消息。推特允许我们使用推特应用编程接口或 **Tweepy** 挖掘任何用户的数据。这些数据将是从用户那里提取的推文。首先要做的是从 twitter developer 获取消费者密钥、消费者秘密、访问密钥和访问秘密，每个用户都可以轻松获得。这些密钥将帮助应用编程接口进行身份验证。

## API.create_saved_search()

Tweepy 模块中`API`类的 **`create_saved_search()`** 方法用于为认证用户创建保存的搜索。

> **语法:** API.create_saved_search(查询)
> 
> **参数:**
> 
> *   **查询:**搜索的查询。
> 
> **返回:【SavedSearch 类的对象**

**示例 1 :** 创建保存的搜索查询。

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

print("The number of saved searches before create_saved_search() : ", end = "")
print(len(api.saved_searches()))

# query of the new saved search
query = "Tweepy"

# creating the saved search
api.create_saved_search(query)

print("The number of saved searches after create_saved_search() : ", end = "")
print(len(api.saved_searches()))
```

**输出:**

```
The number of saved searches before create_saved_search() : 3
The number of saved searches after create_saved_search() : 4

```

**示例 2 :** 获取新创建的已保存搜索。

```
# query of the new saved search
query = "News"

# creating the saved search
saved_search = api.create_saved_search(query)

# printing the information
print("The saved search " + str(saved_search.id) +
      " was created on : " + str(saved_search.created_at))
print("The query of the saved search is : " + saved_search.query)
```

**输出:**

```
The saved search 1269510986496569349 was created on : 2020-06-07 06:06:20
The query of the saved search is : News

```