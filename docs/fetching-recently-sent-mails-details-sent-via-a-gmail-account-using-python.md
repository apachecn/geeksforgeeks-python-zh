# 使用 Python 获取通过 Gmail 账户发送的最近发送邮件的详细信息

> 原文:[https://www . geesforgeks . org/取数-最近发送的邮件-详细信息-通过 gmail 发送-帐户-使用-python/](https://www.geeksforgeeks.org/fetching-recently-sent-mails-details-sent-via-a-gmail-account-using-python/)

在本文中，我们将了解如何使用 Python 通过 Gmail 帐户获取固定数量的最近发送的电子邮件。
本实现中使用的库包括 imaplib、email。您必须手动进入您的 Gmail 帐户[设置](https://mail.google.com/mail/u/0/#settings/fwdandpop)，启用 IMAP 访问。在此之后，只有您可以访问您的 Gmail 帐户，而无需登录浏览器。
在设置页面中，在运行脚本前启用该选项。

![](img/6fa8b99aa78edafe7670e211d52eef9d.png)

**算法:**

*   导入 imaplib、电子邮件、网络浏览器和操作系统模块。
*   与 Gmail 帐户建立 imap 连接。
*   实例化 Gmail 帐户的用户名和密码变量。
*   登录 Gmail 帐户
*   选择发送的邮件。
*   确定要检索的已发送电子邮件的数量 n。
*   迭代 n 封电子邮件，并打印发件人和电子邮件主题。

## 蟒蛇 3

```
# import the modules
import imaplib                             
import email
from email.header import decode_header
import webbrowser
import os

# establish connection with Gmail
server ="imap.gmail.com"                    
imap = imaplib.IMAP4_SSL(server)

# intantiate the username and the password
username ="username@gmail.com"
password ="********"

# login into the gmail account
imap.login(username, password)              

# select the e-mails
res, messages = imap.select('"[Gmail]/Sent Mail"')  

# calculates the total number of sent messages
messages = int(messages[0])

# determine the number of e-mails to be fetched
n = 3

# iterating over the e-mails
for i in range(messages, messages - n, -1):
    res, msg = imap.fetch(str(i), "(RFC822)")    
    for response in msg:
        if isinstance(response, tuple):
            msg = email.message_from_bytes(response[1])

            # getting the sender's mail id
            From = msg["From"]

            # getting the subject of the sent mail
            subject = msg["Subject"]

            # printing the details
            print("From : ", From)
            print("subject : ", subject)
```

**输出:**

**输出**

![](img/66ccc518a9c48b4cea22c0fa1355733b.png)