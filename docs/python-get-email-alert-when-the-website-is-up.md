# Python |网站上线时收到邮件提醒

> 原文:[https://www . geesforgeks . org/python-get-email-alert-当网站启动时/](https://www.geeksforgeeks.org/python-get-email-alert-when-the-website-is-up/)

在本文中，我们将学习如何使用一个简单的 Python 脚本来检查是否有任何网站正在运行或关闭。我们将使用 Python 的 [requests](https://www.geeksforgeeks.org/get-post-requests-using-python/) 库发送**【get】**请求，**【smtplib】**库在网站上线时发送电子邮件通知。这意味着我们不需要每次都检查。我们的 Python 程序会在网站运行时通过电子邮件通知我们。
这个脚本只是检查一个网站是否正常。如果它是向上的，那么它将发送一封关于这个的电子邮件，如果它是向下的，那么它将继续检查，并且当站点将是向上的时候，它将发送一封电子邮件并且终止。
**安装:**
转到命令提示符，写下此命令:

```py
pip install requests, smtplib

```

**以下是步骤:**

*   将整个代码放入 try 块中，以处理异常。
*   向我们想要的网站发送获取请求。
*   如果网站没有运行，那么我们没有得到回应，从而抛出一个异常。
*   然后在除了块，我们只是打印网站没有运行。
*   如果没有异常抛出，那么这意味着我们得到了回应，网站正在运行。
*   现在创建一个通过 gmail 登录的 SMTP 会话。
*   输入正确的 gmail id 和密码。
*   发送邮件并完成。

**下面是实现:**

## 蟒蛇 3

```py
import smtplib, requests, time
from email.mime.text import MIMEText
from email.mime.multipart import MIMEMultipart

while(1):
    try:
        # Replace the url for your desired website
        url = "https://www.facebook.com/"

        # Send the get request to the website
        r = requests.get(url)

        # creates SMTP session
        s = smtplib.SMTP("smtp.gmail.com", 587)

        # start TLS for security
        s.starttls()

        # Authentication
        s.login("sender_gmail_id", "sender_password")

        # Instance of MIMEMultipart
        msg = MIMEMultipart("alternative")

        # Write the subject
        msg["Subject"]= url + " is working now."

        msg["From"]="sender_gmail_id"
        msg["To"]="receiver_gmail_id"

        # Plain text body of the mail
        text = url + " is running now."

        # Attach the Plain body with the msg instance
        msg.attach(MIMEText(text, "plain"))

        # HTML body of the mail
        html ="<h2>Your site is running now.</h2><br/><a href ='"
             + url + "'>Click here to visit.</a>"

        # Attach the HTML body with the msg instance
        msg.attach(MIMEText(html, "html"))

        # Sending the mail
        s.sendmail("sender_gmail_id", "receiver_gmail_id", msg.as_string())
        s.quit()
        print('sent')
        break
    except:
        print('site is down yet...')
        print('sleeping...')

        # Sleeping for 60 seconds. We can change this interval.
        time.sleep(60)
        print('Trying again')
        continue
```