# Python–API . update _ list()在 Tweepy 中

> 原文:[https://www . geesforgeks . org/python-API-update _ list-in-tweepy/](https://www.geeksforgeeks.org/python-api-update_list-in-tweepy/)

**推特**是一个流行的社交网络，用户在这里分享被称为推文的消息。推特允许我们使用推特应用编程接口或 **Tweepy** 挖掘任何用户的数据。这些数据将是从用户那里提取的推文。首先要做的是从 twitter developer 获取消费者密钥、消费者秘密、访问密钥和访问秘密，每个用户都可以轻松获得。这些密钥将帮助应用编程接口进行身份验证。

## API.update_list()

Tweepy 模块中`API`类的 **`update_list()`** 方法用于更新列表。

> **语法:** API.update_list(参数)
> 
> **参数:**
> 
> *   **列表 _id :** 列表的 id。
> *   **slug :** slug 的列表中，还得提到 owner_id/owner_screen_name。
> *   **名称:**列表名称。
> *   **模式:**列表的模式。
> *   **描述:**列表的描述。
> *   **所有者 _id :** 列表所有者的 id。
> *   **所有者 _ 屏幕 _ 名称:**列表所有者的屏幕名称。
> 
> **返回:**类列表的一个对象

**示例 1 :** 更改列表名称。

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
list_id = print("Before using update_list() method")
print("The name of the list is : " + api.get_list(list_id = list_id).name)

# the new name of the list
new_name = "Modified List"

# updating the list
api.update_list(list_id, name = new_name)

print("After using update_list() method")
print("The name of the list is : " + api.get_list(list_id = list_id).name)
```

**输出:**

```
Before using update_list() method
The name of the list is : Sample List
After using update_list() method
The name of the list is : Modified List

```

**示例 2 :** 更新列表的描述。

```
# the screen name of the owner of the list
owner_screen_name =

# the ID of the list
list_id = print("Before using update_list() method")
print("The description of the list is : " + api.get_list(list_id = list_id).description)

# the new description of the list
new_description = "This list is to test the Twitter API."

# updating the list
api.update_list(list_id, description = new_description)

print("After using update_list() method")
print("The description of the list is : " + api.get_list(list_id = list_id).description)
```

**输出:**

```
Before using update_list() method
The description of the list is : 
After using update_list() method
The description of the list is : This list is to test the Twitter API.

```