# Python–API . get _ list()在 Tweepy 中

> 原文:[https://www . geesforgeks . org/python-API-get _ list-in-tweepy/](https://www.geeksforgeeks.org/python-api-get_list-in-tweepy/)

**推特**是一个流行的社交网络，用户在这里分享被称为推文的消息。推特允许我们使用推特应用编程接口或 **Tweepy** 挖掘任何用户的数据。这些数据将是从用户那里提取的推文。首先要做的是从 twitter developer 获取消费者密钥、消费者秘密、访问密钥和访问秘密，每个用户都可以轻松获得。这些密钥将帮助应用编程接口进行身份验证。

## API.get_list()

Tweepy 模块中`API`类的 **`get_list()`** 方法用于获取指定的列表。

> **语法:** API.get_list(list_id/slug，owner_id/owner_screen_name)
> 
> **参数:**
> 
> *   **列表 _id :** 列表的 id。
> *   **鼻涕虫:**列表中的鼻涕虫。
> *   **所有者 _id :** 列表所有者的 id。
> *   **所有者 _ 屏幕 _ 名称:**列表所有者的屏幕名称。
> 
> **返回:**类列表的一个对象

**例 1 :** 取一个列表，打印其名称和描述。

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

# fetching the list
list = api.get_list(list_id = list_id)

# printing the information
print("The name of the list is : " + list.name)
print("The description of the list is : " + list.description)
```

**输出:**

```
The name of the list is : Modified List
The description of the list is : This list is to test the Twitter API.

```

**示例 2 :** 获取不存在的列表时引发异常。

```
# the ID of the non-existent list
list_id = 

# fetching the list
list = api.get_list(list_id = list_id)
```

**输出:**

```
raise TweepError(error_msg, resp, api_code=api_error_code)
tweepy.error.TweepError: [{'code': 34, 'message': 'Sorry, that page does not exist.'}]

```