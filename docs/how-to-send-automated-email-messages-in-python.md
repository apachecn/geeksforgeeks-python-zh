# 如何在 Python 中发送自动电子邮件

> 原文:[https://www . geeksforgeeks . org/如何用 python 发送自动电子邮件/](https://www.geeksforgeeks.org/how-to-send-automated-email-messages-in-python/)

在本文中，我们将看到如何发送自动电子邮件，其中包括发送文本消息、重要照片和重要文件等。在 Python 中。

为此，我们将使用两个库:电子邮件和 [smtplib](https://www.geeksforgeeks.org/send-mail-gmail-account-using-python/) ，以及 MIMEMultipart 对象。此对象有多个子类；这些子类将用于构建我们的电子邮件。

*   **mimetext:** consists of simple words. This will be the body of the email.
*   **mime image:** This will allow us to add an image to the email.
*   **Mimeoudio:** If we want to add an audio file, we can do it easily with this subclass.
*   **MimeApplication:** This can be used to add any content or any other attachments.

## 逐步实施

**步骤 1:** 导入以下模块

## 蟒蛇 3

```
from email.mime.text import MIMEText
from email.mime.image import MIMEImage
from email.mime.application import MIMEApplication
from email.mime.multipart import MIMEMultipart
import smtplib
import os
```

**步骤 2:** 让我们建立一个到我们的电子邮件服务器的连接。

*   Provide the server address and port number to start our **SMTP** connection.
*   Then we will use **SMTP** . **ehlo** Send **EHLO** (extend hello) command.
*   Now, we will use **SMTP** . **Start tls** Enable Transport Layer Security ( **TLS** ) encryption.

## 蟒 3

```
smtp = smtplib.SMTP('smtp.gmail.com', 587)
smtp.ehlo()
smtp.starttls()
smtp.login('YourMail@gmail.com', 'Your Password')
```

**第三步:**现在，构建消息内容。

*   After initializing the msg variable, assign the **mimemultipart** object to the msg variable.
*   The **mimetext** function will be used to attach text.

## 蟒 3

```
msg = MIMEMultipart()
msg['Subject'] = subject
msg.attach(MIMEText(text))
```

**第四步:**我们来看看如何附加图片和多个附件。

**附加图像:**

*   First, the image is read as binary data.
*   Use **mimeimage** to attach image data to **mimemultipart** , and we use **OS** to add the given file name. **Base name**

## 蟒 3

```
img_data = open(one_img, 'rb').read()
msg.attach(MIMEImage(img_data, 
                     name=os.path.basename(one_img)))
```