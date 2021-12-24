# Python–API . report _ spam()在 Tweepy 中

> 原文:[https://www . geesforgeks . org/python-API-report _ spam-in-tweepy/](https://www.geeksforgeeks.org/python-api-report_spam-in-tweepy/)

**推特**是一个流行的社交网络，用户在这里分享被称为推文的消息。推特允许我们使用推特应用编程接口或 **Tweepy** 挖掘任何用户的数据。这些数据将是从用户那里提取的推文。首先要做的是从 twitter developer 获取消费者密钥、消费者秘密、访问密钥和访问秘密，每个用户都可以轻松获得。这些密钥将帮助应用编程接口进行身份验证。

## API.report_spam()

Tweepy 模块中`API`类的 **`report_spam()`** 方法用于报告用户为认证用户。

> **语法:**API . report _ spam(id/screen _ name/user _ id，perform_block)
> 
> **参数:**仅使用 3 个选项之一:
> 
> *   **id :** 指定用户的 id 或屏幕名称。
> *   **user_id :** 指定用户的 id，当有效的用户 ID 也是有效的屏幕名称时，用于区分帐户。
> *   **screen_name :** 指定用户的屏幕名称，当有效的屏幕名称也是用户 id 时，用于区分帐户。
> *   **perform_block:** 表示报告的账户是否也应该被冻结。
> 
> **返回:**用户类的对象

**示例 1 :** 报告并阻止以下用户:
![](img/8da53542541b344c917b1a23ecfd6fc3.png)

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

# the account to be reported
screen_name = "twitter"

# reporting the account
api.report_spam(screen_name = screen_name)
```

**输出:**
![](img/a5c69dcbe13dc108f5f03815069b2eec.png)

**例 2 :** 只报以下账户(不要屏蔽):
![](img/8da53542541b344c917b1a23ecfd6fc3.png)

```py
# the account to be reported
screen_name = "twitter"

# do not block
perform_block = False

# reporting the account
api.report_spam(screen_name = screen_name, perform_block = perform_block)
```

**输出:**
![](img/8da53542541b344c917b1a23ecfd6fc3.png)