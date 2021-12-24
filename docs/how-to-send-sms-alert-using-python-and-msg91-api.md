# 如何使用 Python 和 MSG91 API 发送短信提醒

> 原文:[https://www . geesforgeks . org/how-send-SMS-alert-use-python-and-msg 91-API/](https://www.geeksforgeeks.org/how-to-send-sms-alert-using-python-and-msg91-api/)

在我们的大学时代，我们最常忘记我们的日常课程，对吗？为了每天跟踪课程，我们可以使用 Python 向他们的手机发送关于他们课程的通知(即短信提醒)。

我们需要使用两个功能: **http 模块**和 **MSG91 API** 发送短信。

```
import http.client as ht

conn = ht.HTTPSConnection("api.msg91.com")
```

这里我们在 http 模块中导入 http 客户端函数(因为我们使用我们的系统作为客户端，使用 msg91 api 服务作为服务器)，并使用 HTTPSConnection 函数与 SMS API Service (MSG91)建立连接。

建立连接时，我们需要在数据包中发送两个主要参数(即报头和有效载荷)。

**报头:**在报头中，我们将发送我们的 MSG91 API 的认证密钥。当然，上下文文本只是上下文类型，也就是有效载荷的类型。我们以 JSON 格式发送所有有效载荷信息，因此上下文类型将是 JSON。

```
headers = {# Paste your MSG91 API Key
           'authkey' : "", 
           'content-type': "application/json"}
```

您需要在 MSG91 中创建一个帐户，并且需要在 MSG91 中创建一个 API 密钥来发送短信。

**有效载荷:**大家都知道有效载荷是数据发送或接收的重要环节。在这里，我们发送发送者标识、路线、国家以及消息和接收者手机号码。其中发件人标识只是发件人姓名。它的长度必须为 6，并且应该只包含字母字符。如果您想在国际上发送短信，请使用 0 作为国家代码，否则使用 91 进行印度通信。

```
payload = '''{"sender": "MSGAPI",
              "route": "4",
              "country": "91",
              "sms": [
                {
                  "message": "Welcome X, Today you have PC class",
                  "to": [
                    "9090XX8921"
                  ]
                },
                {
                  "message": "Welcome Y, Today you have WT Class",
                  "to": [
                    "901X83XX01"
                  ]
                }
              ]
            }'''
```

现在我们需要发送连接请求以及这个报头和有效载荷。这里我们使用 POST 方法来建立连接。一旦请求被发送，应用编程接口将把消息发送给接收者，我们已经提到了 JSON 数组。然后，应用编程接口向我们确认状态代码为 200，消息为成功。

```
# importing the module
import http.client as ht

# establishing connection
conn = ht.HTTPSConnection("api.msg91.com")

# determining the payload
payload = '''{"sender": "MSGAPI",
              "route": "4",
              "country": "91",
              "sms": [
                {
                  "message": "Welcome GeeksForGeeks, Today you have PC class",
                  "to": [
                    "9090XX8921"
                  ]
                },
              ]
            }'''

# creating the header
headers = {
    'authkey': "", 
    'content-type': "application / json"
}

# sending the connection request
conn.request("POST", "/api / v2 / sendsms", payload, headers)

res = conn.getresponse()
data = res.read()

# printing the acknowledgement
print(data.decode("utf-8"))
```