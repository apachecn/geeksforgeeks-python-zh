# Python–API . destroy _ saved _ search()在 Tweepy 中

> 原文:[https://www . geesforgeks . org/python-API-destroy _ saved _ search-in-tweepy/](https://www.geeksforgeeks.org/python-api-destroy_saved_search-in-tweepy/)

**推特**是一个流行的社交网络，用户在这里分享被称为推文的消息。推特允许我们使用推特应用编程接口或 **Tweepy** 挖掘任何用户的数据。这些数据将是从用户那里提取的推文。首先要做的是从 twitter developer 获取消费者密钥、消费者秘密、访问密钥和访问秘密，每个用户都可以轻松获得。这些密钥将帮助应用编程接口进行身份验证。

## API.destroy_saved_search()

Tweepy 模块中`API`类的 **`destroy_saved_search()`** 方法用于删除已验证用户的已保存搜索。

> **语法:** API.destroy_saved_search(id)
> 
> **参数:**
> 
> *   **id :** 要销毁的已保存搜索的 id。
> 
> **返回:【SavedSearch 类的对象**

**示例 1 :** 删除保存的搜索。

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

print("The number of saved searches before destroy_saved_search() : ", end = "")
print(len(api.saved_searches()))

# query of the saved search
id = 1269510986496569349

# deleting the saved search
api.destroy_saved_search(id)

print("The number of saved searches after destroy_saved_search() : ", end = "")
print(len(api.saved_searches()))
```

**输出:**

```py
The number of saved searches before destroy_saved_search() : 5
The number of saved searches after destroy_saved_search() : 4

```

**示例 2 :** 删除所有保存的搜索。

```py
# fetching all the saved searhces
saved_searches = api.saved_searches()

print("The number of saved searches before destroy_saved_search() : ", end = "")
print(len(saved_searches))

# deleting all the saved search
for saved_search in saved_searches:
    api.destroy_saved_search(saved_search.id)

print("The number of saved searches after destroy_saved_search() : ", end = "")
print(len(api.saved_searches()))
```

**输出:**

```py
The number of saved searches before destroy_saved_search() : 4
The number of saved searches after destroy_saved_search() : 0

```