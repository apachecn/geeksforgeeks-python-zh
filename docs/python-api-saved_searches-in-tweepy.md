# Python–API . saved _ searches()在 Tweepy 中

> 原文:[https://www . geesforgeks . org/python-API-saved _ searches-in-tweepy/](https://www.geeksforgeeks.org/python-api-saved_searches-in-tweepy/)

**推特**是一个流行的社交网络，用户在这里分享被称为推文的消息。推特允许我们使用推特应用编程接口或 **Tweepy** 挖掘任何用户的数据。这些数据将是从用户那里提取的推文。首先要做的是从 twitter developer 获取消费者密钥、消费者秘密、访问密钥和访问秘密，每个用户都可以轻松获得。这些密钥将帮助应用编程接口进行身份验证。

## API.saved _ searches()

Tweepy 模块中`API`类的 **`saved_searches()`** 方法用于获取已认证用户的已保存搜索。

> **语法:**API . saved _ search()
> 
> **参数:**无
> 
> **返回:【SavedSearch 类的对象列表**

**示例 1 :** 打印查询和保存的搜索的 ID。

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

# fetching the saved searches
saved_searches = api.saved_searches()

# printing the information
for saved_search in saved_searches:
    print("The ID of this saved search is : " + str(saved_search.id))
    print("The query of this saved search is : " + saved_search.query, end = "\n\n")
```

**输出:**

```
The ID of this saved search is : 1269502915346980864
The query of this saved search is : geeks

The ID of this saved search is : 1269502963724115972
The query of this saved search is : geeksforgeeks

The ID of this saved search is : 1269503225993900032
The query of this saved search is : computer

```

**例 2 :** 统计保存的搜索次数。

```
# fetching the saved searches
saved_searches = api.saved_searches()

# printing the number of saved searches
print(len(saved_searches))
```

**输出:**

```
3

```