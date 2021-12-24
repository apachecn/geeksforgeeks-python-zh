# Python–API . destroy _ list()在 Tweepy 中

> 原文:[https://www . geesforgeks . org/python-API-destroy _ list-in-tweepy/](https://www.geeksforgeeks.org/python-api-destroy_list-in-tweepy/)

**推特**是一个流行的社交网络，用户在这里分享被称为推文的消息。推特允许我们使用推特应用编程接口或 **Tweepy** 挖掘任何用户的数据。这些数据将是从用户那里提取的推文。首先要做的是从 twitter developer 获取消费者密钥、消费者秘密、访问密钥和访问秘密，每个用户都可以轻松获得。这些密钥将帮助应用编程接口进行身份验证。

## API.destroy_list()

Tweepy 模块中`API`类的 **`destroy_list()`** 方法用于删除列表。

> **语法:**API . destroy _ list(owner _ screen _ name/owner _ id，list_id/slug)
> 
> **参数:**
> 
> *   **所有者 _id :** 列表所有者的 id。
> *   **所有者 _ 屏幕 _ 名称:**列表所有者的屏幕名称。
> *   **列表 _id :** 列表的 id。
> *   **鼻涕虫:**鼻涕虫的列表中，还得提到 ownerid/owner_screen_name。
> 
> **返回:**类列表的一个对象

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

# the screen name of the owner of the list
owner_screen_name = 

# the ID of the list
list_id = 

# deleting the list
api.destroy_list(owner_screen_name, list_id = list_id)
```

该列表将被删除。

**示例 2 :** 使用`get_list()`方法验证列表是否被删除。

```
# the screen name of the owner of the list
owner_screen_name = 

# the ID of the list
list_id = print("Before using destroy_list() method")
if api.get_list(list_id):
    print("The list exists.")

# deleting the list
api.destroy_list(owner_screen_name, list_id = list_id)

print("After using destroy_list() method")
try:
    api.get_list(list_id)
except:
    print("The list does not exists.")
```

**输出:**

```
Before using destroy_list() method
The list exists.
After using destroy_list() method
The list does not exists.

```